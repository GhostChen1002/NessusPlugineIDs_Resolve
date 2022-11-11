# 漏洞概要

SSH Server 已設定為允許使用 Weak Key Exchange Algorithms。


---

# 漏洞敘述

> CVE : 

SSH Server 已設定為允許使用 Weak Key Exchange Algorithms。

這是基於 IEFT 草案文檔 Key Exchange (KEX) Method Updates and Recommendations for Secure Shell (SSH) draft-ietf-curdle-ssh-kex-sha2-20。第 4 節列出關於不應該和不能啟用的 Key Exchange Algorithms，包含以下演算法。

- diffie-hellman-group-exchange-sha1
- diffie-hellman-group1-sha1 
- gss-gex-sha1-*
- gss-group1-sha1-*
- gss-group14-sha1-*
- rsa1024-sha1

> ⚠️該套件只會檢查 SSH Server 的選項，不會檢查軟體版本是否有漏洞。


---

# 修補方式

1. 禁用 Weak Algorithms。


---
