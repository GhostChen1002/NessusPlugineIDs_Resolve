# 漏洞敘述

> CVE : CVE-2013-4841

HP StoreVirtual 4000 和 StoreVirtual VSA Software(前稱為 LeftHand Virtual SAN Application) 都為美國 HP 公司適用於虛擬化環境的存儲設備。StoreVirtual 4000 是一套基於 LeftHand 操作系統的橫向擴展存儲平台。StoreVirtual VSA Software 是一套軟體定義的虛擬存儲設備。

HP StoreVirtual 4000 和 StoreVitual VSA Software 中 LeftHand OS 10.5 version(Include before versions) 中的 dbd_manager 中存在安全漏洞，攻擊者可以利用該漏洞遠程執行任意程式碼。


---

# 修補方式

1. 將 LeftHand OS Version 升級至 11.0(or later)。


---
