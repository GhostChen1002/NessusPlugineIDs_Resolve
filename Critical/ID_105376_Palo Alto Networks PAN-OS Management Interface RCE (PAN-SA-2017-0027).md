# 漏洞敘述

> CVE : CVE-2017-15944

目標主機上執行 Palo Alto Networks PAN-OS 受到管理介面中的一個 RCE(Remote Command Execute) 弱點影響，原因為在處理 HTTP Request 時，不當驗證使用者提供輸入所致。未經驗證的攻擊者可以惡意利用，透過一系列特殊的 Requests，造成在最高權限使用者內容中的 RCE。


---

# 修補方式

1. 升級至 Palo Alto Networks PAN-OS 6.1.19 / 7.0.19 / 7.1.14 / 8.0.6 版或更新版本。


---
