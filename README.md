# dk-tw-citySelector.js

台灣縣市地區選單，不需資料庫。

(Demo)[http://dennykuo.github.io/dk-tw-citySelector/]

## 安裝

### 擇一使用下列方式

#### 使用 Bower

```
bower install dk-tw-cityselector --save
```

or

#### [下載檔案](https://github.com/dennykuo/dk-tw-citySelector/archive/master.zip)

## 使用方式

### 套件依賴jQuery，在網頁中引入js檔案如下

```
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>
<script src="dk-tw-citySelector.min.js"></script>
```

### 網頁中置入「縣市選單」、「區域選單」、「郵遞區號輸入框(選擇性)」

```
<form id="myForm">
    <select id="county" name="county"></select>
    <select id="district" name="district"></select>
    <!-- 若不需使用郵遞區號欄位可刪除下列input或設type="hidden" -->
    <!-- 若需允許修改則刪去readonly 屬性 -->
    <input id="zip" name="zip" value="" type="text" placeholder="郵遞區號" readonly>
</form>
```

### 呼叫應用

參數設定如下：
$('父元素').dk_tw_citySelector('縣市選單', '區域選單', '郵遞區號input');

```
$(function() {
    $('#myForm').dk_tw_citySelector('#county', '#district', '#zip');
});
```

## 進階使用

### 只顯示部分縣市選單

(目前只限縣市，無法設定其下區域)

縣市選單加上 data-custom 屬性，並輸入要顯示的縣市名稱在其值中
＊正確縣市名稱請依參照dk-tw-citySelector.js檔案

```
<!-- 縣市選單只出現「台北市,台中市,高雄市」 -->
<select id="county" name="county" data-custom="台北市,台中市,高雄市"></select>
```


### 選單預設選定值

選單加上 data-selected 屬性，並輸入要選定的縣市名稱在其值中
＊正確縣市名稱請依參照dk-tw-citySelector.js檔案 

```
<!-- 縣市選單選定值為「台北市」 -->
<select id="county" name="county" data-selected="台北市"></select>

<!-- 區域選單選定值為「中山區」 -->
<select id="district" name="district" data-selected="中山區"></select>

```

### 備註

上面兩種進階用法可同時設定。