# 漏洞概要

可以 Access to the Remote Host。


---

# 漏洞敘述

> CVE : CVE-2005-1794

Remote Desktop Protocol Server(Terminal Service) 的遠端版本容易受到 Man-in-The-Middle(MiTM) Attack。RDP Client 在設置加密時不會驗證 Server 的身分。

能夠攔截來自 RDP Server 流量的攻擊者可以在不被發現的情況下與 Client 和 Server 建立加密。這種性質的 MiTM Attack 允許攻擊者獲取傳輸的任何敏感資訊，包括身分驗證憑據(Authentication Credentials)。

存在此缺陷是因為 RDP Server 存儲了一個公開的 Hard-Coded(硬編碼) RSA Pricate Key。特權網路位置中的任何攻擊者可以使用該密碼進行此攻擊。

> 💡Hard Code/Hard Coding(硬編碼/寫死) : 是指在軟體實作上，將輸出或輸入的相關參數（例如：路徑、輸出的形式或格式）直接以常數的方式撰寫在原始碼中，而非在執行期間由外界指定的設定、資源、資料或格式做出適當回應。一般被認定是種反模式或不完美的實作，因為軟體受到輸入資料或輸出格式的改變就必須修改原始碼，對客戶而言，改變原始碼之外的小設定也許還比較容易。
>
> 但寫死的狀況也並非完全只有缺陷，因某些封裝需要或軟體本身的保護措施，有時是必要的手段。除此之外，有時候因應某些特殊的需求，製作出簡單的應用程式，應用程式可能只會執行一次或者有限的幾次，抑或永遠只應付某種單一需求，利用寫死來縮短開發的時間也是一種不錯的決策。


---

# 修補方式

1. 如果支援，則強制使用 SSL 作為服務的 Transport Layer。
2. 在 Microsoft Windows OS 上，系統 -> 進階系統設定 -> 遠端 -> 選擇設置 "Allow connections only from computers running Remote Desktop with Network Level Authentication(僅允許來自執行含有網路層級驗證之遠端嘬面的電腦進行連線)"。


---
