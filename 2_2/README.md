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

![ETH_DS](imgs/ETH_DS_2.png)

<br>

### 狀態資料

狀態資料以 MPT 的形式儲存在 StateDB 中。MPT 是兼具 Merkle Tree & Patricia Tree 特點的一種新的樹狀資料結構。

MPT 特點：

* 可以儲存任意長度的 key-value pairs。
* 具備 Merkle Tree 的特點，可以用於節點快速校驗。
* 能夠很快速的根據 key 查到 value。

MPT 中包含 shortNode，fullNode，valueNode 還有 hashNode 這四種節點。

shortNode 與 fullNode 是分枝節點，他們可以有個自的子節點。但要注意 shortNode 只能有一個子節點，而 fullNode 可以有多個。

valueNode 與 hashNode 是葉子節點。valueNode 用於儲存資料，值為從 root 節點到當前節點的路徑上所有節點的 key 之合。hashNode 用於儲存資料庫中其他節點的 hash 值。


<br>

### 區塊鏈

ETH 區塊鏈的結構有 2 點與 BTC 區塊鏈相同：

1. ETH 區塊鏈也是由父區塊的 hash 值將區塊連接在一起（指向前一個區塊的指針）。

2. ETH 區塊鏈也是由區塊頭跟區塊體組成。區塊頭與區塊體結構如下：

![DS3](imgs/ETH_DS_3.png)

<br>

// TODO introduce above picture //p35

