# 漏洞概要

Remote SSH Server 設置允許使用 Weak Encryption Algorithms 或不使用 Algorithm。


---

# 漏洞敘述

> CVE : 

Nessus 檢測 Remote SSH Server 設置為使用 Arcfour Stream Cipher 或不使用 Cipher。由於 Weak Keys 的問題，RFC 4253 建議不使用 Arcfour。


---

# 修補方式

1. 請聯繫供應商。
2. 關閉 Arcfour cipers。

修改 `/etc/ssh/sshd_config` 設定檔。

```bash
# 在最後添加以下內容，並去掉 arcfour, arcfour128, arcfour256 等弱加密演算法。
Ciphers aes128-ctr,aes192-ctr,aes256-ctr,aes128-cbc,3des-cbc
```

保存後，重新啟動服務 `service sshd restart` or `service ssh restart`。

> 💡`ssh_config` 與 `sshd_config` 都是 SSH Server 的配置文件，兩者區別於 `ssh_config` 是針對 Client 端配置文件，`sshd_config` 是針對 Server 端配置文件。


---
