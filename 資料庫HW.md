# 資料庫學習重點
```
重點一
資料階層
=>data hierarchy==>Bit（位元）→Byte（字元）→Field（資料欄）→Record（資料錄）→Table（資料表）→Data Base（資料庫）
資料表(table)分所謂
1.欄位(field)
2.紀錄(record)
資料庫(Database)
資料(data)與資訊(information)
資料(data)未經整理沒有處理整合=沒用
資訊(imformation)經過整理有完整概要能使用的資源=>有用
檔案管理系統v.s.資料庫各有的優缺點
檔案管理系統(如word)
優點:設計簡單
缺點:資料重複儲存,缺乏整合，無法保持檔案一致性，資料不可共用分享
資料庫
優點:缺少重複儲存，檔案保持一致，資料獨立性，存取效率提高，較保障隱私
缺點:存取速度慢，資料須正規化

II.資料庫理論:
資料模型（data model）: 
   Network data model[1969,Charles Bachman]
   Hierarchical data model[60年代,IBM]
   relational Data Model[1969, Edgar F. Codd]
   
   Object-oriented data model
   Multi-dimensioncal data model[data warehouse  vs Data Mall]

資料庫系統 ANSI/SPARC 架構[略]
內部層（Internal Level）：實際儲存資料的結構。
外部層（External Level）或稱視界層（View Level）：使用者或是應用程式所看到的部分。
概念層（Conceptual Level）：內部層與外部層之間的橋樑（資料庫管理師（DBA）看的整體部分）。

III.資料庫管理系統
資料的運算 CRUD== Create(建立), Read(讀取), Update(更新), Delete(刪除)
執行資料運算的語法: SQL(Structured Query Language)  
DDL|DML|DCL
DDL=>資料定義語言(Data Definition Language)=>是SQL語言集中負責資料結構定義與資料庫物件定義的語言
DML=>數據操縱語言(Data Manipulation Language)=>是用於資料庫操作，對資料庫其中的物件和資料執行存取工作的編程語句
DCL=>資料控制語言(Data Control Language)=>在SQL語言中，是一種可對資料存取權進行控制的指令
IV.大數據與新興資料庫
4.1.Big data的特色: 3V vs 5V
  Big Data  3V’s ==>Volume(資料大小) ,Velocity(資料輸入輸出的速度),Variety(多樣性)
  Big Data  5V’s ==>Volume(資料大小) ,Velocity(資料輸入輸出的速度),Variety(多樣性),Value(價值) and Veracity(真實性)
4.2.大數據興起激發出新興資料庫發明===> NoSQL 
名詞解釋:是對不同於傳統的關聯式資料庫的資料庫管理系統的統稱。
NoSQL資料庫採用各種資料模型 (例如：文件、圖形、鍵值、內存和搜尋等) 來存取和管理資料。這些類型的資料庫透過放寬傳統關聯式資料庫的一些資料一致性限制
補充:傳統關聯式資料庫的差異=>約束條件太嚴謹無法快速存取(完整性約束)
完整性約束包括：
實體完整性
參照完整性
用戶定義完整性
補充
正規化=>減少資料庫中資料冗餘，增進資料的一致性
```
# 參考資料
```
http://www.wun-ching.com.tw/img/Books_files/D049e4-9789862368602-trial.pdf
```
# I.基本觀念
### 資料階層data hierarchy
```
Bit（位元）→Byte（字元）→Field（資料欄）→Record（資料錄）→Table
（資料表）→Data Base（資料庫）
```
```
•	資料庫軟體（database software），通常又稱為資料庫管理系統（database management system，DBMS）
11-1 　資料庫、資料與資訊(續)
•	資料是組織成一個個的層次
–	字元、欄位、記錄及資料檔案
課本 P.383
11-1 　資料庫、資料與資訊(續)
•	每個位元組代表單一字元（character），它可以是一個數字（4）、字母（R）、空白、標點符號（?）或其他符號（&）。
•	欄位（field）是由一或多個相關的字元或位元組所組成
–	欄位名稱（field name）
–	欄位大小（field size）
–	資料型態（data type） 
課本 P.384
11-1 　資料庫、資料與資訊(續)
•	記錄（record）是一群相關欄位的組合
–	主鍵（primary key）是一個可唯一識別檔案中每筆記錄的欄位
•	資料檔案（data file）是一群相關記錄的集合
課本 P.384-385
11-1 　資料庫、資料與資訊(續)
•	檔案維護（file maintenance）指保持資料是最新的各個程序
課本 P.385
11-1 　資料庫、資料與資訊(續)
•	驗證（validation，或確認）是指將資料與一組規則或數值進行比對，以判斷資料是否符合規範的程序
課本 P.386
11-2 　檔案處理系統 vs. 資料庫
課本 P.387-388
11-2 　檔案處理系統 vs. 資料庫
課本 P.387
11-2 　檔案處理系統 vs. 資料庫(續)
課本 P.388
11-2 　檔案處理系統 vs. 資料庫(續)
課本 P.389
11-2 　檔案處理系統 vs. 資料庫(續)
•	資料庫方法的缺點
–	可能更複雜
–	需要更多的記憶體和處理能力
–	可能資料更容易被入侵
課本 P.389
11-2 　檔案處理系統 vs. 資料庫(續)
•	Web 的功能之一是提供資訊
課本 P.389
11-2 　檔案處理系統 vs. 資料庫(續)
課本 P.390
11-2 　檔案處理系統  vs. 資料庫(續)
•	資料模型（data model）是由定義資料庫如何組織資料的規則及標準所組成。
課本 P.391
科技最前線 11-2 ：大數據
大數據的特徵
•	專家經常以 3 個 V 來描述大數據的特徵： volume（數量）、velocity（速度）以及 variety（多樣性）
–	Volume（數量）指的是個人和機構產生的資料量
–	Velocity（速度）指的是處理資料的速率
–	Variety（多樣性）指的是資料能呈現或儲存的多種格式，以便讓人們或電腦程式運用
課本 P.392
科技最前線 11-2：大數據(續)
大數據的來源和用途
•	企業產生大數據的方式之一是收集顧客行為
課本 P.392
科技最前線 11-2：大數據(續)
資料視覺化
•	資料視覺化（data visualization）指的是將資料以圖像方式表達成圖表或地圖等各種圖形格式，目的是讓結果資訊更容易被理解
課本 P.392
11-3 　資料庫管理系統
•	資料字典（data dictionary），有時也稱為資料儲存庫（repository），內含有關資料庫中每個檔案，以及這些檔案中每個欄位的資料。
課本 P.393
11-3 　資料庫管理系統(續)
•	DBMS 提供幾種工具讓使用者和程式能擷取和維護資料庫中的資料
課本 P.394-395
11-3 　資料庫管理系統(續)
•	查詢（query）是一種從資料庫取得特定資料的要求（request）。
•	查詢語言（query language）是由簡單的、類似英文的敘述所組成，可讓使用者指定想要顯示、列印、儲存、更新或刪除的資料
•	結構化查詢語言（Structured Query Language，SQL）是一種讓使用者能夠管理、更新和擷取資料的熱門查詢語言
課本 P.394
11-3 　資料庫管理系統(續)
•	大部分 DBMS 中都包含以例查詢（query by example，QBE）功能， 它使用圖形化使用者介面來協助使用者擷取資料。
課本 P.394
11-3 　資料庫管理系統(續)
•	表單（form），有時也稱為資料輸入表單（data entry form），是個螢幕上的視窗，提供某塊區域可輸入或修改資料庫中的資料。
•	報表輸出程式（report writer）， 也稱為報表產生器（report generator），讓使用者能夠在螢幕上設計報表、擷取資料放入報表中，然後顯示或列印該報表
課本 P.395
11-3 　資料庫管理系統(續)
課本 P.396
11-3 　資料庫管理系統(續)
•	資料庫會因為硬體故障、軟體問題、人為疏失或火災洪水等災害而受損或毀壞。
課本 P.396-397
```
