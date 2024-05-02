---
marp: true
theme: uncover
class:
  - lead
  - invert
paginate: true
---
<!-- _paginate: false -->

# Crawling with API

---

# 有一天...

---

<!-- _paginate: false -->

![bg](../images/teacher_says_1.png)

---

1. `BeautifulSoup4`
2. `Selenium`

---

:bulb: 尋找在網頁上的位置耗時
:bulb: 額外將抓下的資料結構化

---

<!-- _paginate: false -->

![bg](../images/teacher_says_2.png)

---

![bg](https://divethru.com/wp-content/uploads/2021/03/feeling-confused-1200x675.jpg)

---

1. `BeautifulSoup4`
2. `Selenium`
3. <mark>Request API</mark>

---

## 獲取 API 的常見方式
1. `get`
2. `post`

---
<!-- _paginate: false -->
![bg](../images/search.gif)

---

# 找不到怎麼辦？

---

![width:1000px](https://i.imgur.com/z0HVmWn.png)

---

![width:1000px](https://i.imgur.com/iwWUBw2.png)

---

![width:1000px](https://i.imgur.com/TPRnjyN.png)

---

![width:1000px](https://i.imgur.com/wqGfEOp.png)

---

![width:1000px](https://i.imgur.com/SDDY0mV.png)

---

![width:1000px](https://i.imgur.com/qbhtrSK.png)

---

```python
import requests
# 直接在 URL 夾帶參數
full_url = "https://api-fact-checker.line-apps.com/pub/v1/zhtw/articles/..."
# get method
response = requests.get(full_url)
print(response.json())  # 輸出網頁內容
```

```python
# 參數不夾帶在URL
base_url = "https://api-fact-checker.line-apps.com/pub/v1/zhtw/articles/verified/"
params = {"size": 9, "sort": "updatedAt", "loc": "home"}
response = requests.get(base_url, params=params)
print(response.json())
```

---
### 小試身手
![width:800px](../images/teacher_says_3.png)

---

![width:1000px](https://i.imgur.com/XkbqdhJ.png)

---

![width:1000px](https://i.imgur.com/aDW4wmk.png)

---

```python
url = 'https://www.railway.gov.tw/tra-tip-web/tip/tip001/tip112/querybytime'
payload = {
    "csrf": "2cad25fc-a9c1-4852-b57e-b720a4259ef3",
    "startStation": "0900-基隆",
    "endStation": "1010-萬華",
    "transfer": "ONE",
    "rideDate": "2024/05/01",
    "startOrEndTime": "true",
    "startTime": "00:00",
    "endTime": "23:59",
    "trainTypeList": "ALL",
    "queryClassification": "NORMAL",
    "query": "查詢"
}
response = requests.post(url, data=payload)
print(response.text)
```

---

### 小試身手
![width:800px](../images/teacher_says_4.png)

---