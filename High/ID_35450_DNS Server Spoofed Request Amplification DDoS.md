# 漏洞敘述

> CVE : CVE-2006-0987

DNS Server 會回應任何要求。攻擊者可以查詢 `.(根區域)` 的名稱伺服器(NS)，並獲得比原始要求更大的回應。並透過偽造來源 IP 位址，攻擊者可以利用這個 `Amplification`，使用 DNS Server 來針對第三方主機引發 Denial-of-Service(DoS) 攻擊。


---

# 修補方式

1. 限制從公共網路訪問 DNS Server。
2. 重新配置，使 DNS Server 拒絕此類的查詢。

```
//   zone "." IN {  
//         type hint;  
//         file "named.ca";  
//   };
```

## Windows

### 設定 ACL

只允許特定 IP 或網段可以進行 recursive query。

```bash
dnscmd [ServerName | ServerIP] /resetlistenaddresses \[ListenAddress&gt]
```

### 關閉 recursive query

關閉 recursive query。

```bash
dnscmd [ServerName | ServerIP] /Config /NoRecursion {1|0}
# 0 : 默認，啟用 recursive query。1 : 關閉 recursive query。
```

## Linux 

以下都是針對 BIND 的設定檔  `/usr/local/etc/namedb/named.conf` 進行設定。如果有變更 named.conf，需要重新啟動服務 `/etc/init.d/named restart` or `/usr/local/etc/rc.d/named restart`。

### 設定 ACL

只允許特定 IP 或網段可以進行 recursive query。

```bash
Acl "allowed_IP" {
    192.168.0.0/16;
};

options {
    ...
    allow-recursion { allowed_IP; };
    # allow-recursion { none; }; 將 recursive query 關閉。
    ...
}
```

### 關閉 recursive query

```bash
options {
    ...
    allow-query { none; };
    ...
}
```


---
