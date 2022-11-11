# 漏洞概要

Remote DNS Server 容易受到 Cache Snooping Attack。

---

# 漏洞敘述

> CVE : 

Remote DNS Server 回應對未設置 Recursion Query 的第三方 Domain 查詢。

可能允許攻擊者確定最近通過該 Name Server 解析了那些 Domain，因此最近訪問那些主機。

E.g. 如果攻擊者對您的公司是否使用特定金融機構的在線服務感興趣，他們將此攻擊來建立有關該金融機構的公司使用情況統計模型。當然，該攻擊還可用於 Find B2B Partners、Web-Surfing Patterns、External Mail Servers，或更多。

> ⚠️如果是外部網路無法訪問到內部 DNS Server，則攻擊僅限於內部網路。可能包括員工、顧問和訪客網路或 WiFi 連接上的用戶。

---

# 修補方式

1. 請聯繫 DNS 軟件的供應商以獲取修復。
2. 對 BIND 的設定檔 `/usr/local/etc/namedb/named.conf` 進行設置。如果有變更 named.conf，需要重新啟動服務 `/etc/init.d/named restart` or `/usr/local/etc/rc.d/named restart`。

```bash
options {
    ...
    allow-recursion { none; };
    allow-query-cache { none; };
    ...
}
```


---
