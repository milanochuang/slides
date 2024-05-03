---
title: R crawler
marp: true
theme: default

---

<!--會寫字寫句子，但不代表寫得出好文章-->
# 網路爬蟲 :spider: 

----

# 資料 data
<!--我們分析語言時需要什麼？資料。如果沒有資料，即使再會寫程式我們也巧婦難為無米之炊-->

----

# 巧婦難為無米之炊

---

### 今天可以學到什麼？

<font size=6>
    
1. 認識JSON檔
2. 認識網頁基本架構（html+CSS, maybe Javascript?）
3. 爬蟲的基本概念
4. ```readLines()```
5. ```rvest()```
6. 怎麼找CSS或XPath呢？
7. 範例：PTT爬蟲
8. 範例：PChome爬蟲
    
</font>

---

# 認識JSON檔

----

## 所以到底什麼是JSON檔?
* **JavaScript Object Notation** 的縮寫
* 常用於網站上的**資料呈現、傳輸**
* 可在 JSON 之內加入**相同的基本資料類型**

----

## JSON檔長什麼樣子？
```r
library(jsonlite)
metroCity_heroes <- '{
  "squadName": "Super hero squad",
  "homeTown": "Metro City",
  "formed": 2016,
  "secretBase": "Super tower",
  "active": true,
  "members": [
    {
      "name": "Molecule Man",
      "age": 29,
      "secretIdentity": "Dan Jukes",
      "powers": [
        "Radiation resistance",
        "Turning tiny",
        "Radiation blast"
      ]
    },
    {
      "name": "Madame Uppercut",
      "age": 39,
      "secretIdentity": "Jane Wilson",
      "powers": [
        "Million tonne punch",
        "Damage resistance",
        "Superhuman reflexes"
      ]
    },
    {
      "name": "Eternal Flame",
      "age": 1000000,
      "secretIdentity": "Unknown",
      "powers": [
        "Immortality",
        "Heat Immunity",
        "Inferno",
        "Teleportation",
        "Interdimensional travel"
      ]
    }
  ]
}'
metroCityLIST <- fromJSON(metroCity_heroes)
metroCityLIST['squadName']
class(metroCityLIST)
```
---
```r
$squadName
"Super hero squad"
"list"
```

----

## JSON as array
```r
friends_starring <- '[
    {
        "character": "Rachel Green",
        "star": "Jennifer Aniston"
    },
    {
        "character": "Monica Geller",
        "star": "Courteney Cox"
    },
    {
        "character": "Phoebe Buffay",
        "star": "Lisa Kudrow"
    },
    {
        "character": "Joey Tribbiani",
        "star": "Matt LeBlanc"
    },
    {
        "character": "Chandler Bing",
        "star": "Matthew Perry"
    },
    {
        "character": "Ross Geller",
        "star": "David Schwimmer"
    }
]'

fs_df <- fromJSON(friends_starring)
for (i in 1:nrow(fs_df)){
    print(paste("誰飾演", fs_df[i, "character"], "：", fs_df[i, "star"]))
}
```
---
```r
[1] "誰飾演 Rachel Green ： Jennifer Aniston"
[1] "誰飾演 Monica Geller ： Courteney Cox"
[1] "誰飾演 Phoebe Buffay ： Lisa Kudrow"
[1] "誰飾演 Joey Tribbiani ： Matt LeBlanc"
[1] "誰飾演 Chandler Bing ： Matthew Perry"
[1] "誰飾演 Ross Geller ： David Schwimmer"
```

----

```r
head(fs_df)
```
```csvpreview {header"true"}
       character,             star
    Rachel Green, Jennifer Aniston
   Monica Geller,    Courteney Cox
   Phoebe Buffay,      Lisa Kudrow
  Joey Tribbiani,     Matt LeBlanc
   Chandler Bing,    Matthew Perry
     Ross Geller,  David Schwimmer
```

---

# 認識網頁基本架構
## html+CSS, maybe Javascript?

----

## 先祝大家聖誕快樂 :christmas_tree: 

----

## 說到聖誕節，大家想到什麼？

----

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/82/Tannenbaum_Geschenke_und_der_Mond_2007_by-RaBoe.jpg/800px-Tannenbaum_Geschenke_und_der_Mond_2007_by-RaBoe.jpg" style="background:none; border:none; box-shadow:none; max-width:50%;">

----

* 樹本身：html
* 裝飾品、燈串：CSS
* 讓燈一閃一閃：Javascript

----

## 沒概念？
### 來看看實際上長什麼樣子

----

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Basic HTML Page</title>
</head>
<body>
    <p style = "color: red;">Hello HTML</p>
</body>
</html>
```

----

```html
/*style.css*/
#html {color: red;}
#css {color: blue;}

<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <link rel="stylesheet" href="style.css">
    <title>Basic HTML Page</title>
</head>
<body>
    <p>Hello HTML</p>
    <p>Hello CSS</p>
    <p class="topic">Hello HTML</p>
    <p class="topic">Hello CSS</p>
    <p id="frame">Hello HTML</p>
    <p id="frame">Hello CSS</p>
</body>
</html>
```

---

# 爬蟲基本概念

----

## 既然網頁是聖誕樹...

----

## 那爬蟲就是...找裝飾品！
<img src="https://media4.giphy.com/media/l2YWiHWiFHwmbwIso/giphy.gif" style="background:none; border:none; box-shadow:none; max-width:150%;">

----

## 寫成程式會變怎樣呢

<font size=4>**LET** (urlLIST, dataLIST) **BE** (empty list, empty list)&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160;```urlLIST=地點清單，dataLIST=購物車```
**FOR EACH** index page URL **DO** &#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;```在每一個購物中心裡```
&#160; &#160; &#160; &#160;**ADD** article page URL **IN** urlLIST &#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; ```找到每一棵你想找的聖誕樹```
**FOR EACH** article page URL **IN** urlLIST &#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160;```從每一棵聖誕樹上```
&#160; &#160; &#160; &#160;Each_Page_Data **←** **PARSE(** article page URL **)** &#160; &#160;&#160; &#160;&#160; &#160;&#160; &#160;&#160; &#160;&#160; &#160;&#160; &#160;&#160; &#160;&#160;&#160;```從特定的位置找到你想找的裝飾品```
&#160; &#160; &#160; &#160;**ADD** Each_Page_Data **TO** dataLIST &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160; &#160; &#160; &#160;&#160;&#160;```把裝飾品裝到籃子裡```</font>

---

# ```readLines()```

----

### 如果你要爬的網頁結構相對簡單```readLines()```是相對好的選擇

----

# 為什麼?

----

## Guideline:

1. 呼叫內建的 ```readLines()``` 函式
2. 將html解析成字串向量（vector）
3. 用正規表達式來清理資料 <br/>
Mama Mia, here we go again!

----

### 第一次爬行
<font size=5>[The One Where Monica Gets a New Roommate (The Pilot-The Uncut Version)](https://livesinabox.com/friends/season1/101pilot.htm)</font>
```r
library(magrittr)
fs_s1e1 <- readLines("http://livesinabox.com/friends/season1/101pilot.htm")
head(fs_s1e1)
```
```r
[1] "<html>"                                                                              
[2] ""                                                                                    
[3] "<head>"                                                                              
[4] "<title>The One Where Monica Gets a New Roomate (The Pilot-The Uncut Version)</title>"
[5] "</head>"                                                                             
[6] ""
```

----

我們要分析在影集六人行裡面，每個角色各有幾句台詞...
觀察資料，你發現了什麼？
```r
character_pattern <- "Joey:|Monica:|Ross:|Rachel:|Chandler:|Phoebe:"
found_character <- grepl(pattern = character_pattern, fs_s1e1)
fs_s1e1[found_character] %>%
    head()
```
```r
[1] "<p align=\"left\"><font size=\"3\"><b>Monica:</b> There's nothing to tell! He's just some guy" 
[2] "<p align=\"left\"><font size=\"3\"><b>Joey:</b> C'mon, you're going out with the guy! There's" 
[3] "<p align=\"left\"><font size=\"3\"><b>Chandler:</b> <font color\"#0000FF\">All right Joey, be"
[4] "<p align=\"left\"><font size=\"3\"><b>Phoebe:</b> Wait, does he eat chalk?</font></p>"         
[5] "<p align=\"left\"><font size=\"3\"><b>Phoebe:</b> Just, 'cause, I don't want her to go through"
[6] "<p align=\"left\"><font size=\"3\"><b>Monica:</b> Okay, everybody relax. This is not even a"
```

----

現在來清理不要的標籤: ```<p></p>```、```<b></b>```、```<strong></strong>```
```r
table_result <- fs_s1e1[found_character] %>%
    gsub(pattern = "<p(>|.*)(<b>|<strong>)", replacement = "") %>%
    gsub(pattern = "(</b>|</strong>).*", replacement = "") %>%
    gsub(pattern = "(:\\s)|:", replacement = "") %>%
    table()
sort(table_result, decreasing = TRUE)
```
```r
 .
          Monica          Rachel            Ross            Joey        Chandler 
              72              48              47              41              39 
          Phoebe Ross and Rachel 
              19               1
```

----

```r
barplot(sort(table_result, decreasing = TRUE), las = 1, cex.names = 0.7, main = "Number of Scripts in Episode 1, Season 1")
```
<img src="https://i.imgur.com/sNyGhkR.png" style="background:none; border:none; box-shadow:none; max-width:100%;">

----

### 我們發現了什麼?
[La La Land](http://www.imdb.com/title/tt3783958/) -> 按下右鍵查看原始碼，出事了阿伯
```r
head(readLines("http://www.imdb.com/title/tt3783958/"))
```
```r
Warning in readLines("http://www.imdb.com/title/tt3783958/"): 於 'http://
www.imdb.com/title/tt3783958/' 找到不完整的最後一列
```
```r
[1] "<!DOCTYPE html><html lang=\"en-US\" xmlns:og=\"http://opengraphprotocol.org/schema/\" xmlns:fb=\"http://www.facebook.com/2008/fbml\"><head><script>"
[2] "var ue_t0=ue_t0||+new Date();"                                                                                                                      
[3] ""                                                                                                                                                   
[4] "window.ue_ihb = (window.ue_ihb || window.ueinit || 0) + 1;"                                                                                         
[5] "if (window.ue_ihb === 1) {"                                                                                                                         
[6] ""
```

---

# ```rvest()```

----

* 直接擷取想要的html標籤

```r
url <- "http://www.imdb.com/title/tt3783958/"
lalaland <- read_html(url)
rating <- lalaland %>%
    html_nodes(css = "div[class='RatingBar__RatingContainer-sc-85l9wd-0 hNqCJh TitleBlock__HideableRatingBar-sc-1nlhx7j-4 bhTVMj'] span[class='AggregateRatingButton__RatingScore-sc-1ll29m0-1 iTLWoV']") 
rating
```
```r
{xml_nodeset (1)}
[1] <span class="AggregateRatingButton__RatingScore-sc-1ll29m0-1 iTLWoV">8.0</span>
```

----

* 直接取得標籤內的文字（也就是去除標籤）
```r
rating <- lalaland %>%
    html_nodes(css = "div[class='RatingBar__RatingContainer-sc-85l9wd-0 hNqCJh TitleBlock__HideableRatingBar-sc-1nlhx7j-4 bhTVMj'] span[class='AggregateRatingButton__RatingScore-sc-1ll29m0-1 iTLWoV']")  %>%
    html_text() %>%
    as.numeric()
rating
```
```r
8
```

----

* 另外一種做法: 使用 **XPath**

```r
rating <- lalaland %>%
    html_nodes(xpath = "/html[1]/body[1]/div[2]/main[1]/div[1]/section[1]/section[1]/div[3]/section[1]/section[1]/div[1]/div[2]/div[1]/div[1]/a[1]/div[1]/div[1]/div[2]/div[1]/span[1]") %>%
    html_text() %>%
    as.numeric()
rating
```
```r
8
```

---

## 怎麼找CSS或XPath呢？

----

## 一般情形
#### 請先下載擴充程式

----

<font size=6>

* Chrome: [ChroPath](https://chrome.google.com/webstore/detail/chropath/ljngjbnaijcbncmcnjfhigebomdlkcjo?utm_source=chrome-ntp-icon)
    * (網頁任意處右鍵) -> 檢查 -> 元素 -> (右側「樣式」列的最右側，若沒看到則按">>") -> (檢查元素) -> (複製CSS或XPath)
* Firefox: [SelectorsHub](https://addons.mozilla.org/zh-TW/firefox/addon/selectorshub/?utm_source=addons.mozilla.org&utm_medium=referral&utm_content=search)
    * (網頁任意處右鍵) -> 檢測 -> 檢測器 -> (右側「樣式」列的最右側，若沒看到則按向下箭頭樣式) -> (檢查元素) -> (複製CSS或XPath)
    * Alternatives: 移動游標至欲檢測之目標上方 -> (右鍵) -> SelectorsHub -> "Copy Rel cssSelector" or "Copy Rel XPath"

</font>

----

![](https://i.imgur.com/PsH79uk.png)

----

## 特殊情形
#### [Abe Hiroshi's Official Website](http://abehiroshi.la.coocan.jp/)

----

![](https://i.imgur.com/Unz3Y4s.jpg)

----

```r
url <- "http://abehiroshi.la.coocan.jp/"
AbeHiroshi <- read_html(url)
AbeHiroshi
```
```r
{html_document}
<html>
[1] <head>\n<meta http-equiv="Content-Type" content="text/html; charset=UTF-8 ...
[2] <frameset cols="18,82">\n<frame src="menu.htm" marginheight="0" marginwid ...
```

----

![](https://i.imgur.com/byWCUSW.png)

----

![](https://i.imgur.com/9IZNgGE.png)

---

# 範例一
# PTT 爬蟲

----

```r
# Find the url of the index page (Places where you want to buy Christmas tree)
url_vec <- c()
pageNum <- 9501:1
urls <- paste("https://www.ptt.cc/bbs/movie/index", pageNum,".html", sep="")
```

----

![](https://i.imgur.com/BJC8pyw.png)

----

```r
# Write a function that would collect all the url from the index page (Collect all the Christmas trees from the mall)
crawlURL <- function(url){
  raw_html <- read_html(url)
  article_link_xpath <- "//div[@class='title']/a"
  article_links <- raw_html %>%
    html_nodes(xpath = article_link_xpath) %>%
    html_attr("href")
  article_links <- paste("https://www.ptt.cc", article_links, sep = "")
  return(article_links)
}
head(crawlURL("https://www.ptt.cc/bbs/movie/index9501.html"))
```
```r
[1] "https://www.ptt.cc/bbs/movie/M.1638707290.A.BD5.html"
[2] "https://www.ptt.cc/bbs/movie/M.1638707967.A.706.html"
[3] "https://www.ptt.cc/bbs/movie/M.1638710184.A.723.html"
[4] "https://www.ptt.cc/bbs/movie/M.1638710747.A.B9A.html"
[5] "https://www.ptt.cc/bbs/movie/M.1638713288.A.28D.html"
[6] "https://www.ptt.cc/bbs/movie/M.1638715229.A.F82.html"
```

----

```r
# Consider the time issue, let's crawl the first five url.
for (i in 1:5){
  url_vec <- c(url_vec, crawlURL(urls[i]))
}
```

----

```r
library(rvest)
# Write a function that would collect all the data you want only using the url as the parameter of the function
# Locate the decorations hung on the Christmas tree you want to take 
article_detail <- function(url){
    raw_html <- read_html(url)
    
    # select the css path to locate the data
    author_css <- ".article-metaline:nth-child(1) .article-meta-value"
    title_css <- ".article-metaline-right+ .article-metaline .article-meta-value"
    time_css <- ".article-metaline+ .article-metaline .article-meta-value"
    main_content_css <- "#main-content"
    #ip_css <- ".hl+ .f2"
    push_css <- ".push-tag"
    push_id_css <- ".push-userid"
    push_content_css <- ".push-content"
    push_time_css <- ".push-ipdatetime"
    
    article_detail_info <- list()
    columns <- c(author_css, title_css, time_css, main_content_css, push_css, push_id_css, push_content_css, push_time_css)
    for (i in 1:length(columns)){
        article_content <- raw_html %>%
            html_nodes(css = columns[i]) %>%
            html_text()
        article_detail_info[[i]] <- article_content
    }
    
    names(article_detail_info) <- c("author", "title", "time", "main_content", "push", "push_id", "push_content", "push_time")
    
    # data cleaning process
    article_detail_info$main_content <- article_detail_info$main_content %>%
        gsub(pattern = "\n", ., replacement = "") %>% # 清理斷行符號
        gsub(pattern = "--.+", ., replacement = "") %>% # 去尾
        gsub(pattern = "作者.+:[0-9]{2}\\s[0-9]{4}", ., replacement = "") # 去頭
    #ip_start <- regexpr(pattern = "[0-9]+", article_detail_info$ip)
    #ip_end <- nchar(article_detail_info$ip)
    #article_detail_info$ip <- substr(article_detail_info$ip, start = ip_start, stop = ip_end)
    #article_detail_info$ip <- gsub(pattern = "\n", article_detail_info$ip, replacement = "") # 清理斷行符號
    article_detail_info$push <- gsub(pattern = "\\s", article_detail_info$push, replacement = "")
    article_detail_info$push_id <- gsub(pattern = "\\s", article_detail_info$push_id, replacement = "")
    article_detail_info$push_content <- article_detail_info$push_content %>%
        gsub(pattern = "\\s", ., replacement = "") %>%
        gsub(pattern = ":", ., replacement = "")
    article_detail_info$push_time <- article_detail_info$push_time %>%
        gsub(pattern = "^\\s", ., replacement = "") %>%
        gsub(pattern = "\n", ., replacement = "")
    return(article_detail_info)
}
```

----

```r
# Put all the decoration you have collected into the basket.
article_list = list()
for (i in seq_along(url_vec[1:5])){
  article_list[[i]] <- article_detail(url_vec[i])
}
article_list[[1]]
```
```r
$author
[1] "killeryuan (龍鳥)"
 
$title
[1] "[好雷] 《永恆族》可惜不能是獨立電影"

$time
[1] "Sun Dec  5 20:28:07 2021"

$main_content
[1] "圖文好讀：https://vocus.cc/article/61a9d6f7fd89780001c9f5f7漫威電影宇宙甚麼都好，就可惜在每一部電影、每一個英雄都不能是獨立的，都必須為整體的主軸服務。這種趨勢在正式建立「宇宙」後被確立，在票房大獲成功後更成為「天條」，所以蜘蛛人必須成為鋼鐵人小弟，所以索爾和驚奇隊長必須離開地球，所以永恆族必須把三個故事塞在一集電影講完。~~~~~~~~~~~~~~~~~~~ 雷文 主文分隔線 ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~沒錯，三個。首先是永恆族團隊在幾千年前來到地球，保護古代地球人與怪物戰鬥到近現代，這是第一個。數千年的戰鬥讓永恆族身心俱疲，地球人彼此戰爭的殘酷也讓部分成員對保護地球產生質疑，最後團隊四散，摸索著與地球人共存，這是第二個。最後則是永恆族的主宰天神族的真正計畫被揭露出來，包括永恆族的真正起源、怪物的真相、以及保護地球的真正意義，這導致團隊真正的內鬨、對彼此下殺手，但也在最後找到了「團結」的真諦，這是第三個。看看，這根本是把三集《美國隊長》搬在一起演：第一集是古代、第二集是團隊從內部瓦解，最後一集是彼此的內戰。從投入的場景預算、編劇對每個角色的描寫、動作場面的編排等各方面來看，製作方是很認真、很嚴肅的想把這電影「拍好」，幾乎每個永恆族都有自己專屬的故事線，也盡可能在有限的鏡頭和時間中詮釋出各自的性格特色。前後情節也都能做到互相呼應，至少不會像《蜘蛛人２：電光之戰》一樣幾條劇情線完全沒有交集。而永恆族的選角方面，上映前有不少人抱怨太過「政治正確」，選了許多非白人演員，或是讓角色成為聾啞人與同性戀等。撇開政治議題不談，這些演員其實都是老面孔，常常出沒在美劇或是電影中，演技是有保證的。至少不會像恐怖電影一樣黑人只負責死，又或是讓角色莫名其妙開始發表政確演講。但盡管電影長度已經相當長了（這又不是DC），但時間還是不夠。聾啞女英雄雖然能夠很自然地融入在每個場景中，但屬於她的故事基本沒有，觀眾無從瞭解她。黑人同性戀英雄似乎只是為了帶出「因為愛而重拾對人類的信心」的題材，但這似乎不是同性戀也可以吧？最倒楣就是女主角，因為劇情濃度太高，她必須是一個專門推動主線的角色，因此變成像是許多手遊主角一樣，幾乎毫無個人特色，只是為了推動劇情或是介紹設定而動作。明明台詞是最多的，但記憶點卻最少，就連能力都像是為了最後大戰而硬湊出來的。正因為能看得出來製作團隊對電影的認真對待，對於最終的成果只能說可惜，可惜最後只能交出一部普通偏上的漫威電影：有大場面、有香豔場景、有幽默笑料、帶出下一部電影的鋪陳，然後就沒了。不過，對於賦予它的期望和為了達成期望而付出的努力，還是必須給予肯定的，最終成果畢竟仍然是一部相當有娛樂性的動作大片。實在非戰之罪，任何一個三部曲給壓縮在一部電影裡面最多就只能這樣了。總分：3.5/5劇情：3/5角色：3/5動作：4/5特效：4/5"

$push
[1] "→" "→" "推" "→" "噓" "推" "→"

$push_id
[1] "StarLeauge" "will0620"   "AppleAlice" "AppleAlice" "butmyass"  
[6] "odddriver"  "f126975955"

$push_content
[1] "目前來看他就是獨立電影，暫和MCU沒任何的連結"     
[2] "可惜不能是影集"                                  
[3] "很推這個觀點，我也覺得這部很好看，但要探討的議題"
[4] "很多，濃度太高，變得很不好處理"                  
[5] "儘管"                                            
[6] "希望拍成影集"                                    
[7] "他不是獨立電影啊片尾還是跟MCU連在一起了"         

$push_time
[1] "12/05 20:54" "12/05 21:09" "12/05 21:30" "12/05 21:30" "12/05 22:33"
[6] "12/05 23:19" "12/06 12:25"
```

---

# 範例二
# PCHome 爬蟲

----

先來簡單看看網站結構
```r
pchome_test <- readLines("http://ecshweb.pchome.com.tw/search/v3.3/?q=macbook%20pro"); pchome_test
```

----

# 你發現了什麼？

----

## 找不到資料
* 這是因為文字不是存在html的標籤之中
* 可使用擴充元件來驗證
[Quick Javascript Switcher](https://chrome.google.com/webstore/detail/quick-javascript-switcher/geddoclleiomckbhadiaipdggiiccfje)

----


* 安裝好 Quick JavaScript Switcher 之後，點選圖示關閉 JavaScript
* 頁面產品資訊消失了

----

![](https://github.com/yaojenkuo/r-crawler/raw/274a9c6e75e4fd580fd3c1c6ebb4ceb7e6a735d8//img/ch0903.png)

----

* 網站動態用 JavaScript 查詢後端資料庫
* 所以打開 Chrome 開發者工具
* 點選 Network 頁籤

----

![](https://github.com/yaojenkuo/r-crawler/raw/274a9c6e75e4fd580fd3c1c6ebb4ceb7e6a735d8//img/ch0904.png)

----


* 因為網頁已經讀取完畢，所以裡面沒有內容
* 我們按重新整理

----

![](https://github.com/yaojenkuo/r-crawler/raw/274a9c6e75e4fd580fd3c1c6ebb4ceb7e6a735d8//img/ch0905.png)

----


* 網站動態利用 JavaScript 去後端資料庫查詢的例子，資料多半會在 XHR/JS 裡面
* 我們點選 XHR 檢查
* 點選 results?q=macbook%20pro&page=1&sort=rnk/dc

----

![](https://github.com/yaojenkuo/r-crawler/raw/274a9c6e75e4fd580fd3c1c6ebb4ceb7e6a735d8//img/ch0906.png)

----


* 點選右邊的 Preview 標籤就能夠看到商品資訊

----

![](https://github.com/yaojenkuo/r-crawler/raw/274a9c6e75e4fd580fd3c1c6ebb4ceb7e6a735d8//img/ch0907.png)

----


* 接著我們點選 Headers 標籤將 Request URL 複製貼上到瀏覽器
* 我們大概就知道查詢後的商品資訊是以 JSON 格式在傳送

----

```r
library(jsonlite)
url <- "http://ecshweb.pchome.com.tw/search/v3.3/all/results?q=macbook%20pro&page=1&sort=rnk/dc"
macbook_pro_query <- fromJSON(url)
```
```r
$QTime
[1] 82

$totalRows
[1] 11106

$totalPage
[1] 100

$range
$range$min
[1] ""

$range$max
[1] ""


$cateName
[1] ""

$q
[1] "macbook pro"

$subq
[1] ""

$token
[1] "macbook" "pro"    

$isMust
[1] 1

$prods
```

----

```r
library(jsonlite)
url <- "http://ecshweb.pchome.com.tw/search/v3.3/all/results?q=macbook%20pro&page=1&sort=rnk/dc"
macbook_pro_query <- fromJSON(url)
page_nums <- 1:macbook_pro_query$totalPage

urls <- paste("http://ecshweb.pchome.com.tw/search/v3.3/all/results?q=macbook%20pro&page=", page_nums, "&sort=rnk/dc", sep = "")
product_names <- c()
product_descriptions <- c()
product_prices <- c()

for (i in 1:5){
    single_page_query <- fromJSON(urls[i])
    product_names <- c(product_names, single_page_query$prods$name)
    product_descriptions <- c(product_descriptions, single_page_query$prods$describe)
    product_prices <- c(product_prices, single_page_query$prods$price)
    Sys.sleep(sample(2:5, size = 1)) # why sleep
}
mbp_result_df <- data.frame(product_names, product_descriptions, product_prices)
head(mbp_result_df)
```
```r
                                                                         product_names
 1  MacBook Pro 13:Apple M1 chip 8-core CPU and 8-core GPU,256GB-Space Grey(MYD82TA/A)
 2            【Amachine】Type C3.1 極速PD 十合一 HUB for macbook / Surface / ipad pro
 3            【Amachine】TYPE C 3.1極速PD 11合1 HUB(for macbook / Surface / ipad pro)
 4        MacBook Pro 13 :Apple M1 chip 8-core CPU and 8-core GPU,512GB SSD-Space Grey
 5                  New MacBook Pro hub Type-C轉USB轉接器mac轉換頭 多功能充電集線器-T8
 6 MacBook Pro 13 :Apple M1 chip 8-core CPU and 8-core GPU,512GB SSD-Silver(MYDC2TA/A)
                                                                                                
```

---

Reference: [R 語言與網站爬蟲](https://github.com/yaojenkuo/r-crawler)
