# 漏洞敘述

> CVE : CVE-2004-2761

遠端服務在已使用加密 Weak Hashing Algorithm(E.g. MD2, MD4, MD5, SHA1) 簽署 SSL Certificate Chain。這些 Signature Algorithms 容易受到 Collision Attack(碰撞攻擊)。攻擊者可以利用此漏洞生成另一個具有相同 Digital Signature 的 Certificate，從而允許攻擊者偽裝成受影響的服務。


---

# 修補方式

1. 請聯繫證書頒發機構以重新頒發 SSL 證書。


---
