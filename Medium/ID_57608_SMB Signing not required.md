# 漏洞概要

Remote SMB Server 不需要簽署。


---

# 漏洞敘述

> CVE : 

Remote SMB Server 不需要簽署。未經驗證的攻擊者可以利用該漏洞，對 SMB Server 發動攔截式攻擊。


---

# 修補方式

1. 在主機的組態中強制訊息簽署。在 Windows 中，此項目位於原則設定 "Microsoft 網路伺服器:數位簽署通訊(永遠)" 中。在 Samba 中，此設定稱為 "伺服器簽署"。


---
