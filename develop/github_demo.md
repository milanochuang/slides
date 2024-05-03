---
marp: true
theme: uncover
---

<!-- <img src="https://i.imgur.com/AiMpIV1.png" style="background:none; border:none; box-shadow:none; max-width:40%;"> -->
![width:300](https://i.imgur.com/AiMpIV1.png)
# How: git & GitHub

---

## 今天會做什麼呢？
- 什麼是 **git**
- 為什麼要用 **git**
- **GitHub**又是什麼？

----

## 可以帶走什麼呢？
- 屬於你的GitHub帳號
- 你的第一個repository (程式庫)
- 上傳你的第一個程式檔

----

## 首先，找到你的終端機

----

<!--| Windows | Mac OS/Linux | 描述 | 例子|
| -------- | -------- | -------- |-------- |
| exit     | exit    | 關閉視窗     |```exit```|
| cd | cd | 修改資料夾 | ```cd test```
| dir|ls|條列資料檔案|```ls```|
| copy | cp | 複製檔案 | ```copy c:\test\test.txt c:\windows\test.txt```
|move|mv|移動檔案|```move c:\test\test.txt c:\windows\test.txt```
|mkdir|mkdir|新建目錄|```mkdir testdirectory```
|del|rm|刪除目錄/檔案|```del c:\test\test.txt del```-->

<img src="https://i.imgur.com/JOFBofR.png" style="background:none; border:none; box-shadow:none; max-width:100%;">

:bulb: [**今晚，我想來點更多的 command line**](https://carolhsu.gitbooks.io/django-girls-tutorial-traditional-chiness/content/intro_to_command_line/README.html)

---

# 到底什麼是 **git** ?

----

<img src="https://i.imgur.com/8e8hSHn.gif" style="background:none; border:none; box-shadow:none; max-width:100%;"><br/><br/>

### 先來看看搜尋git會出現什麼圖片。

----

<img src="https://i.imgur.com/MxL7Lez.png" style="background:none; border:none; box-shadow:none; max-width:100%;"><br/>
<!-- ![](https://i.imgur.com/MxL7Lez.png) -->
告訴我，你看到了什麼

----

## git: 版本管理工具
<img src="https://i.imgur.com/lNFBzPJ.gif" style="background:none; border:none; box-shadow:none; max-width:100%;">

----

## git就是小老師，他可以...
- 把作業(program)集中在置物櫃(repository)裡
- 知道置物櫃位置，小老師給你置物櫃鑰匙(SSH)
- 看聯絡簿了解昨天的作業(status)
- 把作業先交給小老師(add)

----


- 告訴小老師你的修改，寫在便條紙上(commit)
- 小老師提交(push)到置物櫃(repository)裡
- 班上第一名的那個當作業範本(Master)
- 借別班第一名作業修(ㄔㄠ)改(ㄒㄧˊ)(clone)
- 知道第一名作業改了什麼(pull)

---

# 為什麼要用git?

----

# 什麼是GitHub

---

# 先來找小老師

----

<br/>

### For Mac OS user：
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" 
brew install git 
```
### For Windows user：[點我](http://git-scm.com/download/win)

---

# 從置物櫃開始

----

[**GitHub 網站註冊**](https://github.com) 
<img src="https://i.imgur.com/iEBipyZ.jpg" style="background:none; border:none; box-shadow:none; max-width:75%;"><br/>
驗證 -> 2-5 -> Student -> 全勾 -> Continue for free

----

### 建立ssh key (索取置物櫃鑰匙)
1. 打開終端機(Git Bash)
2. 輸入```ssh-keygen```
```bash
# For mac and Windows user
$ ssh-keygen                                   # 產生金鑰

# Generating public/private algorithm key pair.
> Enter file in which to save the key (/Users/you/.ssh/id_ed25519):   # 金鑰存放路徑，直接按 Enter
> Created directory '/Users/you/.ssh/id_ed25519'.
> Enter passphrase (empty for no passphrase):    # 密碼，可設定可不設定，設定的話每次上傳會多需要輸入一次密碼
> Enter same passphrase again:                   # 再輸入一次密碼
> The key fingerprint is:                        # 之後會顯示你的 fingerprint，到這裡就完成 key 的產生了
```

----

```bash
$ cat /User/milanochuang/.ssh/id_rsa.pub           # 讀取檔案內容
> ssh-rsa ~一連串金鑰~ milanochuang           # 從 ssh-rsa 複製到 username@pc-name
```

----

### 回到GitHub將鑰匙跟置物櫃配對
![width:800](https://i.imgur.com/WnTCFKu.png)

----

![width:800](https://i.imgur.com/5Xy4lqO.png)

----

![width:800](https://i.imgur.com/YkT5gqS.png)

----

![width:800](https://i.imgur.com/IZH8aJ6.png)

----

<img src="https://i.imgur.com/SSjGJdM.png" style="background:none; border:none; box-shadow:none; max-width:100%;">

---

# 申請櫃位

----

## 建立第一個 repository
<img src="https://i.imgur.com/a7TBy7v.png" style="background:none; border:none; box-shadow:none; max-width:100%;">

----

## 設定一下...
<img src="https://i.imgur.com/9Z4IzDl.png" style="background:none; border:none; box-shadow:none; max-width:40%;">

:bangbang: 下面三個選項都先不要勾

----

## 開始交作業
```bash
# 先做基本設定
$ git config --global user.email "you@example.com"
$ git config --global user.name "Your Name"
```

----

1. 到桌面或是你喜歡的路徑建立新資料夾
2. 使用終端機導引到你所設立的新資料夾
3. 一行一行地打上GitHub提供給你的指令
```bash
$ cd /Users/milanochuang/Desktop/test
```
```bash
echo "# test" >> README.md   #建立markdown檔，內容為 # test
git init                     #git 初始設定
git add README.md            #設立README Markdown檔
git commit -m "first commit" #附上版本紀錄
git branch -M master         #確認分支
git remote add origin git@github.com:(github id)/(repo name).git   
                             #確認ssh key
git push -u origin master    #提交檔案/程式碼
> Enter passphrase for key '/Users/milanochuang/.ssh/id_rsa': 
                             #輸入剛剛設定的密碼（如果有的話）
```

----

## 到GitHub的Repo確認看看
## 有沒有上傳成功吧！

---

# 放作業到置物櫃

----

現在打開終端機導引至方才新增的資料夾路徑
<img src="https://i.imgur.com/IVcNvdh.png" style="background:none; border:none; box-shadow:none; max-width:70%;">

----

新增一個txt檔

```bash
echo "# test" >> test.txt
```
![width:700](https://i.imgur.com/pS0d9hP.png)

----

## 確認git狀態(看聯絡簿！)

```bash
git status
```

----

![width:600](https://i.imgur.com/B5ocyl9.png)

----

將作業加入git(交給小老師！)
```bash
# 加入特定檔案，則輸入完整檔名
git add #檔名
# 加入全部檔案，則可以輸入點點
git add .
```
---
![width:600](https://i.imgur.com/SmhCt76.png)


----

## 修改紀錄(寫便條紙)
<br/>

```bash
git commit -m "First commit" # <CommitMessage>
```

----

**什麼是一個好的commit message?**
1. 做了什麼事情（What）
2. 為什麼要做這件事情（Why）
3. 用什麼方法做到的（How）

----

## 這是好的commit message嗎？
<br/>

```bash
git commit -m "Fix bugs" # <CommitMessage>
```

----

![width:800](https://i.imgur.com/jpHGDdm.png)
<!-- <img src="https://i.imgur.com/jpHGDdm.png" style="background:none; border:none; box-shadow:none; max-width:70%;"> -->

----

提交程式碼(交作業囉！)
```bash
git push
```

----
![width:800](https://i.imgur.com/z4xxXEB.png)
<!-- <img src="https://i.imgur.com/z4xxXEB.png" style="background:none; border:none; box-shadow:none; max-width:70%;"> -->

---

# 從別人置物櫃拿作業

----

## 一次下載程式碼
```bash
git clone # <cloneaddress>
# https://github.com/milanochuang/SharingAboutGit.git
# https://github.com/chiphuyen/lazynlp.git
```

----
![width:800](https://i.imgur.com/zjy1daQ.png)
<!-- <img src="https://i.imgur.com/zjy1daQ.png" style="background:none; border:none; box-shadow:none; max-width:70%;"> -->

---

# 關於分支

----

## 建立分支
<br/>

```bash
git branch issue1 #<branchname>
git branch
# *master
#  issue1
```
```
  *Master
     |
     o
     |
  issue1
```

----

## 切換分支
<br/>

```bash
git checkout issue1 # <branch>
# Switched to branch 'issue1'

git branch
#  master
# *issue1

# Note: 同時建立與切換分支
git checkout -b <branch>
```

----
```
  Master
     |
     o
     |
  *issue1
```

----

## 打開剛剛的txt檔
## 再多打上"issue1"

----
<!-- <img src="https://i.imgur.com/UeK9yGM.png" style="background:none; border:none; box-shadow:none; max-width:70%;"> -->
![width:800](https://i.imgur.com/UeK9yGM.png)

----

## 在```issue1```的 branch 底下提交
```bash
git add test.txt
git commit -m "添加issue1"
# 不要push
```
```
  Master
     |
     o -----o
            |
         *issue1
```

----

## 切換回```master```分支
<br/>

```bash
git checkout master
# Switch to branch 'master'
```
```
  *Master
     |
     o -----o
            |
          issue1
```
<br/>

打開檔案確認內容是否為更改前的狀態

----

## 合併分支
<br/>

```bash
git merge issue1 # <branch>
```
```
         *Master
            |
     o -----o
            |
          issue1
```
<br/>

打開檔案確認是否為修正後的檔案

----

## 刪除分支
<br/>

```bash
git branch -d issue1 # <branch>
```
```bash
git branch # 確認分支
# *master
```
```
  Master
     |
     o 
```

---

# 一些補充

----

## 什麼是```.gitignore```
## 什麼又是 ```README.md```

----

## Fork 跟 clone 有什麼不一樣？
![width:800](https://i.imgur.com/xaoxGaN.png)
<!-- <img src="https://i.imgur.com/xaoxGaN.png" style="background:none; border:none; box-shadow:none; max-width:90%;"> -->

----

# 只有這些指令嗎？

---

# 謝謝大家