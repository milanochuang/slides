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

<!-- _paginate: false -->

## 有一天...

![width:700px](../images/teacher_says_1.png)

---

1. `BeautifulSoup4`
2. `Selenium`

---

:bulb: 尋找在網頁上的位置耗時
:bulb: 額外將抓下的資料結構化

---

<!-- _paginate: false -->

![width:800px](../images/teacher_says_2.png)

---

1. `BeautifulSoup4`
2. `Selenium`
3. Request API

---

<!-- _paginate: false -->

![width:1000px](../images/search.gif)

---

# 找不到怎麼辦？

---

![width:500px](https://camo.githubusercontent.com/01ee3fd490427e64eb4aea990bc7dadfab24b8d8ed88f1856c073f5485f708b7/68747470733a2f2f756e646f2e696f2f6d656469612f75706c6f6164732f66696c65732f467275737472617465645f70726f6772616d6d65722e6769663f7261773d74727565)

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

## 小試身手

![width:700px](../images/teacher_says_3.png)

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

## 小試身手

![width:700px](../images/teacher_says_4.png)
