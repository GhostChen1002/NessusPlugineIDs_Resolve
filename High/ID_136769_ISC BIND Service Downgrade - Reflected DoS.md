# 漏洞概要

目標主機的 Name Server 受到 Downgrade(服務降級)/Reflected(反射) DoS 漏洞影響。


---

# 漏洞敘述

> CVE : CVE-2020-8616

根據檢測報告中的版本，目標主機上運行的 ISC BIND 9 受到 Performance Downgrade(性能降低) 和 Reflected DoS Vulnerabilities(反射 DoS 漏洞) 的影響。

未經身分驗證的攻擊者可以利用此漏洞降低遞迴服務器的服務質量，或將受到影響的服務器用於反射攻擊中的反射器。


---

# 修補方式

1. 升級到供應商公告中引用的 ISC BIND 版本。


---
