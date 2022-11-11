# 漏洞概要

Remote Name Server 允許運行 nessusd 的主機執行 recursive queries。

---

# 漏洞敘述

> CVE : CVE-1999-0024

可以向 Remote Name Server 查詢第三方名稱。

如果是內部 Name Server，Attack Vector 可能僅限於員工或訪問顧客(如果允許)。

如果您正在探測 Remote Name Server，它允許任何人使用它來解析第三方名稱(E.g. www.nessus.org)。這允許攻擊者對此 Name Server 執行 Cache Poisoning Attack。

如果目標主機允許通過 UDP 進行 Recursive Queries，則目標主機可用於 "Dounce(反彈)" 針對另一個網路或系統進行 DoS Attack。


---

# 修補方式

## Windows

關閉 recursive query。

```bash
dnscmd [ServerName | ServerIP] /Config /NoRecursion {1|0}
# 0 : 默認，啟用 recursive query。1 : 關閉 recursive query。
```

## Linux

1. 對 BIND 的設定檔 `/usr/local/etc/namedb/named.conf` 進行設置。如果有變更 named.conf，需要重新啟動服務 `/etc/init.d/named restart` or `/usr/local/etc/rc.d/named restart`。

```bash
options {
    ...
    allow-recursion { none; };
    allow-query-cache { none; };
    ...
}
```


---
