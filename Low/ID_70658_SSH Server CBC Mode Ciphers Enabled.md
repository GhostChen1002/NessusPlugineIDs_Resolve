# 漏洞概要

SSH Server 已設定為使用 CBC 模式加密。


---

# 漏洞敘述

> CVE : CVE-2008-5161

SSH Server 已設定為支援 CBC(Cipher Block Chaining) 加密。這可能允許攻擊者從加密文字復原純文字訊息。

> ⚠️該套件只會檢查 SSH Server 的選項，不會檢查軟體版本是否有漏洞。


---

# 修補方式

1. 停用 CBC 模式加密，並啟用 CTR 或 GCM 加密模式加密。


---
