# 漏洞概要

此服務使用的 X.509 Certificate Chain 包含 RSA Keys 短於 2048 bits 的證書。


---

# 漏洞敘述

> CVE : 

目標主機發送至少一個 X.509 Certificates 短於 2048 bits 的密鑰。

根據 Certification Authority/Browser(CA/B) 論壇制定的行業標準，2014/01/01 後頒發的 Certificates 必須至少為 2048 bits。

某些瀏覽器 SSL 實現可能會在 2014/01/01 後拒絕小於 2048 bits 的密鑰。此外，某些 SSL Certificate 提供商可能會在 2014/01/01 前吊銷小於 2048 bits Certificates。

> ⚠️如果 Root Certificates 在 2010/12/31 前頒發，則 Nessus 不會標記 RSA 密鑰小於 2048 bits Root Certificates，因為該標準認為它們是豁免的。


---

# 修補方式

1. 將鏈中的證書替換為長度小於 2048 位的 RSA 密鑰，並使用更長的密鑰，並重新頒發由舊證書籤名的所有證書。


---
