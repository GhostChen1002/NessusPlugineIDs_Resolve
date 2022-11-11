# 漏洞概要

Remote SNMP 程式受到允許 Reflection DDoS Attack 漏洞影響。


---

# 漏洞敘述

> CVE : 

Remote SNMP 程式以大量資料回應 `max-repetitions` 值大於正常值的 `GETBULK` 要求。攻擊者可以使用此 SNMP Server，在任意遠端主機上執行 Reflection DDoS Attack。


---

# 修補方式

1. 如果不使用時，停止禁用主機上的 SNMP 服務。如果必須要使用時，請限制並監視對此服務的存取，並考慮變更預設的 `publice` community string。


---
