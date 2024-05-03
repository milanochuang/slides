---
marp: true
---

# Flask
<!-- <font size=5> -->

人工智慧與數位人文
莊昊耘 2023.5.25

<!-- <font size=5> -->

---

## 什麼是 Flask?

----

### 請大家到 `/templates` 打開 `static_index.html`

----

### Flask 就是幫助傳送網頁資料的工具

---

## Build my first Flask Web App

----

## :dart: 今日目標<br><br>
**利用 Flask 打造 Machine Learning Web APP**

----

### 確認材料包
1. `flask_tutorial.ipynb`
2. `model_training.ipynb`
3. `flask_ml_app.ipynb`

----

### 打開 `flask_tutorial.ipynb`

----

## 安裝套件
```bash=
!pip install flask
```

----

### Flask...可以回傳單純文字
```python
from flask import Flask
app = Flask(__name__)

@app.route('/') # ← Website url; try make a change.
def hello_world():
    return 'Hello, World!'

# ↑ One page, one function; one change, one function.
```
```python
app.run(port=5000)
# run app in debug mode on port 5000
```

----

![width:500](https://i.imgur.com/mSwalXa.png)

----
    
### 每做一次更動就要按停止

----

## 既然可以傳送文字...

----

### 回傳 html
```python
@app.route('/aidh')
def static_page():
    return '''
    <html>
    <head>
        <title>Home Page - Microblog</title>
    </head>
    <body>
        <h1>Hello, this is a static webpage!</h1>
    </body>
    </html>'''
```

----

![width:500](https://i.imgur.com/jUaHvDT.png)

----

## 可是助教...

----

* 將上次的 html 檔複製進去 template 資料夾，重新命名為 `index.html`

----

### 直接回傳 html 檔
```python
@app.route('/aidh_file')
def html_file_page():
    return render_template('index.html') # 檔案名稱
```
<!-- 將名字那邊註解起來，要用的時候把它打開 -->

----

![](https://i.imgur.com/7doeFG6.png)

----

### 你也可以新增變數

----

```python
@app.route('/aidh_name')
def html_file_page_name():
    my_name = "Milan"
    return render_template('index.html', someone=my_name) # 檔案名稱
```
<!-- 將名字那邊註解起來，要用的時候把它打開 -->
```htmlembedded=
<!-- @index.html -->
<h1>我，{{someone}}，最喜歡張瑜芸老師了</h1>
```

----

![](https://i.imgur.com/VV024xt.png)

----

### :dart: 小試身手

<font size=6>

1. 將 `index.html` 中新增一個`<a>`標籤
2. 標籤的文字部分輸入為「我的第一個 Web APP」並在標籤中加入超連結 (`<a href="./<route>">我的第一個 Web APP</a>`)
3. 將超連結導向到 `static_index.html`
4. 在 `static_index.html` 新增 `<h2>` 標籤
5. 用以上加入參數的方法，在 `static_index.html` 中的 `<h2>` 標籤中加入文字「<mark>**[你的名字]**</mark> 的第一個 Web APP」

<font>

----

![](https://i.imgur.com/9qraPFe.png)

----

![](https://i.imgur.com/QeAFdab.jpg)

---

## Post method

----

加入 `form.html` 的 body...
```htmlembedded=
<!-- 對應 python 裡面的 result -->
<form method="POST" action="/result"> 
        <input type="text" name="firstname" placeholder="First name">
        <input type="text" name="lastname" placeholder="Last name">
        <button type="submit" class="btn btn-primary">SEND</button>
</form>
    {{ FIRSTNAME }}
    {{ LASTNAME }}
```

----

### 接收網頁傳送的值
```python
app = Flask(__name__)
# default page of our web-app
@app.route('/')
def home():
    return render_template('form.html')

@app.route('/result', methods=['POST'])
def result_intro():
    firstname = request.values['firstname']
    lastname = request.values['lastname']
    return render_template('form.html', FIRSTNAME=firstname, LASTNAME=lastname)
```

----

![](https://i.imgur.com/uNORTNp.png)

----

![](https://memeprod.ap-south-1.linodeobjects.com/user-template/b81fa7d87499a972b9cd55cbdd3cf716.png)

----

### 來看接收的值長什麼樣子
```python
@app.route('/result', methods=['POST']) # route 對應 html 裡面的 action
def result():
    print("這是 request 印出來的樣子：", request)
    print("這是 request.values 印出來的樣子：", dict(request.values))
    print("這是 request.values 印出來的樣子：", list(request.values.keys()))
    print("這是 request.values 印出來的樣子：", list(request.values.values()))
    firstname = request.values['firstname']
    lastname = request.values['lastname']
    return render_template('form.html', FIRSTNAME=firstname, LASTNAME=lastname)
```

----

![](https://i.imgur.com/aJchFTe.png)

---

## Machine Learning APP
### Part 1: model training

----

* 機器學習模型只吃數值資料
* 用多少特徵訓練，也得用相同數量的特徵預測
* 注意轉成數值的資料對應的類別

----

### 打開 `model_training.ipynb`

----

```python
from sklearn import svm
import pandas as pd
from sklearn.model_selection import train_test_split

df = pd.read_csv('./data/mammal_reptile.txt', sep='\t')
df.head()
```

----

```python
from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()
le_df = df.apply(le.fit_transform)
le_df = df.apply(LabelEncoder().fit_transform)
le_df.head()
```

----

```python
features = le_df[["toothed","hair","breathes","legs"]]
target = le_df['species']
```
```python
feat_train, feat_test, target_train, target_test = train_test_split(features, target, test_size=0.2, random_state=0)
```
```python
svm_model = svm.SVC(C=1, gamma='auto', kernel='rbf')
svm_model.fit(feat_train, target_train)
```
```python
predicted_res = svm_model.predict(feat_test)
predicted_labels = le.inverse_transform(predicted_res)
predicted_labels
```

----

### 把模型存起來
```python
import pickle
pickle.dump(svm_model, open('./model/svm_model.pkl','wb'))
```

---

## Machine Learning APP
### Part 2: html

----

* 你的網站主題是什麼？功用是什麼？
* 希望使用者怎麼使用你的網站？
* 所有欄位都必填嗎？還是選填？
* 希望使用者輸入什麼格式？

----

### 複製 `static_index.html` <br>並命名為 `ml_app.html`

----

### 更改標題
```htmlembedded=5
<title>Mammal or not?</title>
```
```htmlembedded=34
<h1>Guessing Mammals</h1>
<h3>Give me features, I will guess if it's mammal or not.</h3>
```

----

## 來看一下 `ml_app.html` 多了什麼吧！

----

### 在 html 中加入輸入欄位
```htmlembedded=
<form action="/predict" method="post">
        <input
          type="text"
          name="toothed"
          placeholder="Do they have tooth? Enter Yes or No."
          required="required"
        />
```
----

## 還需要顯示結果吧！

----

### 讓網頁顯示 Flask 傳過來的文字
```htmlembedded=64
<br />
<br />
{{ prediction_text }}
```

---

## Machine Learning APP
### Part 3: Flask

----

* 需要什麼 method？ POST？
* function 數量 ＝ 頁面 (更動) 數量
* 初始頁面＋預測後顯示 (更動) ＝ 2
* 使用者想看到的是什麼？數字？文字？
* 如果使用者輸入錯誤格式怎麼辦？防呆機制？

----

### 搭建網站後端需要的 Flask
```python
import pickle
app = Flask(__name__)
model = pickle.load(open('./model/svm_model.pkl', 'rb'))
#default page of our web-app
@app.route('/')
def home():
    return render_template('ml_app.html')

#To use the predict button in our web-app
@app.route('/predict', methods=['POST'])
def predict():
    '''
    For rendering results on HTML GUI
    '''
    try:
        int_features = []
        text_features = []
        for value in request.value.values():
            text_features.append(value)
        # text_features = [x for x in request.form.values()]
        for text in text_features:
            if text == "Yes":
                int_features.append(1)
            elif text == "No":
                int_features.append(0)
        final_features = [int_features]
        prediction = model.predict(final_features)
        if prediction[0] == 1:
            output = "No"
        elif prediction[0] == 0:
            output = "Yes"
        return render_template('ml_app.html', prediction_text='Is it a mammal? My answer is {}'.format(output))
    except:
        return render_template('ml_app.html', prediction_text='Something went wrong with your input!')
```

----

```python
app.run(port=8080)  # run app in debug mode on port 8080
```

----

![](https://i.imgur.com/vBweTrP.jpg)

---

## 今日目標

----

## 分工合作
<font size=6>

1. 使用 `iris.txt` 的資料訓練任一機器學習模型，並儲存。
2. 修改 ml_app.html，並依照資料加入適當數量的輸入欄位，使用者得輸入值進行預測。
3. 撰寫一Python Flask，以承接輸入欄位之資料，並以資料預測結果。

<font>

----

## :bulb: 加分
1. 明確的網站介紹與欄位輸入設計
2. 網站設計與美觀
3. 加入防呆機制

---

## 參考資料
<font size=6>

[Integrating Machine Learning into Web Applications with Flask](https://medium.com/analytics-vidhya/integrating-machine-learning-into-web-applications-with-flask-c345118cf08e)

<font>