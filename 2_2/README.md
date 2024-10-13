# 以太坊區塊鏈 (資料結構)

<br>

---

<br>


以太坊的資料儲存可以分為 3 種:

1. __狀態資料__: 以太坊帳戶相關的狀態資料，使用 StatueDB 儲存與管理帳戶，每一個帳戶都是一個 StateObject。

2. __區塊鏈__: 以太坊的核心資料，跟 bitcoin 很像但又有一點進化。

2. __底層資料__: 儲存全部的以太坊資料，以 key-value 的形式存於 LevelDB 中。

<br>

---

Tips: 
    
以太坊資料儲存在 LevelDB 中。

LevelDB 是 Google 推出的一款 key-value database。

目前以太坊中共有 3 個 LevelDB，分別是 BlockDB, StateDB, ExtrasDB。

* BlockDB: 保存區塊主體內容 (包括區塊頭部，與區塊體)。
* StateDB: 保存帳號狀態資料。
* ExtrasDB: 保存交易收據資料以其其他輔助資料。



---

<br>
<br>

## 以太坊資料結構

<br>

// TODO: make a graph

<br>
<br>


## 以太坊狀態資料

<br>

// TODO: introduce

<br>
<br>


## 以太坊區塊鏈

<br>

// TODO: make a graph and introduce

