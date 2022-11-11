# 漏洞概要

SSH Server 設置為允許 MD5 和 96-bit MAC Algorithms。


---

# 漏洞敘述

> CVE : 

SSH Server 設置為允許 MD5 和 96-bit MAC Algorithms。

> ⚠️該套件只會檢查 SSH Server 的選項，不會檢查軟體版本是否有漏洞。


---

# 修補方式

1. 停用 MD5 和 96-bit MAC Algorithms。

## Linux

修改 `/etc/ssh/sshd_config`，添加以下演算法。

```bash
MACs hmac-sha1,umac-64,hmac-sha2-256,hmac-sha2-512,hmac-ripemd160
```

修改保存後，重新啟動服務 `service sshd restart or service ssh restart`。

---
