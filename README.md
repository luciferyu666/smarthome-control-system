# smarthome-control-system
「智慧家控系統」將為家電電器行業提供全面的管理解決方案，涵蓋從銷售、庫存、維修到客戶服務的全流程。系統將包括前端APP、後端伺服器、資料庫及與現有ERP系統的整合。


## 系統目標 ##

「智慧家控系統」主要目的在整合並優化家電電器企業的多項業務流程，通過智能化和自動化手段提升運營效率、降低成本、提高客戶滿意度。

## 系統範圍 ##

系統涵蓋以下主要模組：

- 串聯ERP資料庫
- 行事曆預約鬧鐘提醒功能
- 銷售通路資料管理 / 進、出貨庫存管理
- 維修派工預約功能
- 產品保固登錄管理
- 客戶滿意度評價功能

```
+-----------------+         +-----------------+         +-----------------+
|     用戶 (APP)    | <-----> |   前端應用 (APP)  | <-----> |  後端伺服器       |
+-----------------+         +-----------------+         +-----------------+
       |                            |                            |
       |                            |                            |
       V                            V                            V
+-----------------+         +-----------------+         +-----------------+
|    提交操作        |         |    數據傳輸        |         |    業務邏輯處理    |
+-----------------+         +-----------------+         +-----------------+
                                                               |
                                                               |
                                                               V
                                                      +-----------------+
                                                      |    資料庫           |
                                                      +-----------------+
                                                               |
                                                               |
                                                               V
                                                      +-----------------+
                                                      |    數據同步至ERP  |
                                                      +-----------------+
                                                               |
                                                               |
                                                               V
                                                      +-----------------+
                                                      |    ERP系統         |
                                                      +-----------------+
                                                               ^
                                                               |
                                                               |
                                                      +-----------------+
                                                      |  第三方API (行事曆、通知) |
                                                      +-----------------+
                                                               |
                                                               |
                                                               V
                                                      +-----------------+
                                                      |   通知服務 (FCM)  |
                                                      +-----------------+


+-----------------+        +-----------------+        +-----------------+
|     用戶 (APP)    |        |   前端應用 (APP)  |        |  後端伺服器       |
+-----------------+        +-----------------+        +-----------------+
       |                            |                            |
       |  提交維修申請                |                            |
       |--------------------------->|                            |
       |                            |  發送維修申請數據              |
       |                            |--------------------------->|
       |                            |                            |
       |                            |          處理維修申請            |
       |                            |                            |
       |                            |          生成工單並存入資料庫      |
       |                            |                            |
       |                            |<---------------------------|
       |                            |                            |
       |                            |          自動派工並通知維修人員    |
       |                            |--------------------------->|
       |                            |                            |
       |                            |          發送通知給用戶           |
       |                            |<---------------------------|
       |                            |                            |
       |        查看維修進度            |                            |
       |<---------------------------|                            |
       |                            |                            |
       |       更新維修狀態               |                            |
       |--------------------------->|                            |
       |                            |          同步狀態至ERP系統        |
       |                            |--------------------------->|
       |                            |                            |
       |                            |          通知用戶維修完成        |
       |                            |<---------------------------|
       |                            |                            |
       |        提交評價                |                            |
       |--------------------------->|                            |
       |                            |          存儲評價數據             |
       |                            |--------------------------->|
       |                            |                            |
       V                            V                            V
+-----------------+        +-----------------+        +-----------------+
|     資料庫           | <----> |    ERP系統         | <----> |  第三方API (通知)  |
+-----------------+        +-----------------+        +-----------------+
```
