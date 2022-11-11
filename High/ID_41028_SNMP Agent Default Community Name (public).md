# 漏洞敘述

> CVE : CVE-1999-0517

可以獲取 Remote SNMP Server 的 Default Community Name。

攻擊者可以使用此訊息來獲取有關目標主機的更多訊息，或更改目標系統的配置(如果 Default Community Name 允許此類修改)。


---

# 修補方式

1. 如果不使用 SNMP 服務，可以將其關閉禁用。
2. 過濾此端口的 UDP Packets。
3. 更改 Default Community Strings。


---
