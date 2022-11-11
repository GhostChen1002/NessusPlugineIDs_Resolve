# 漏洞概要

此服務的 SSL 憑證鏈結以未識別的自我簽署憑證結尾。


---

# 漏洞敘述

> CVE : 

此服務的 X.509 憑證鏈結並非由已識別的憑證授權單位簽署。如果目標主機是生產環境中的公共主機，這會造成 SSL 的使用無效，因為任何人都可以對目標主機發動攔截式(MiTM)攻擊。

> ⚠️Nessus 套件不會檢查以未自我簽署，而是由未識別的憑證授權單位簽署的憑證解尾的憑證鏈結。


---

# 修補方式

1. 購買或產生適合此伺服器的 SSL 憑證。


---