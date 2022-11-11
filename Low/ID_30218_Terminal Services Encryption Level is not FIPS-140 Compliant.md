# 漏洞概要

目標主機不符合 FIPS-140 compliant。


---

# 漏洞敘述

> CVE : 

目標主機服務使用的加密設定非 FIPS-140 compliant。


---

# 修補方式

1. 將 RDP 加密等級修改成以下等級。
        i 4. FIPS Compliant

控制面板(Control Panel) -> 管理工具(Adminsitrative Tools) -> 本地安全策略(Local Security Policy) ->安全設置(Security Settings) -> 本地策略(Local Policies) -> 安全選項(Security Options) -> 找到“系統加密：將FIPS兼容算法用於加密、哈希和簽名 （System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing）”選項->右鍵“屬性”->在“本地安全設置”下，選擇“已啟用（E）”，點擊“應用”、“確定”，即可。


---
