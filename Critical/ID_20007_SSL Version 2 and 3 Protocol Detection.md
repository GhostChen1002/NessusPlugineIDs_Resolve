# 漏洞概要

目標主機使用具有已知漏洞的協定對流量進行加密。


---

# 漏洞敘述

目標主機接受使用 SSL 2.0/3.0 連線，這些 SSL 版本受到一些加密漏洞的影響，有以下加密漏洞。

- 具有 CBC 密碼的不安全填補設置。
- 不安全的工作階段重新交涉和恢復配置。

攻擊者可以利用這些漏洞，進行攔截式攻擊(MITM Attack, 中間人攻擊)或解密受影響的服務和客戶端之間的通訊。

雖然 SSL/TLS 可以透過安全的方式選擇通訊協定受支援的最高版本(因此，只有在客戶端和服務氣支援更好時，才會使用這些版本)，但是仍有許多網頁瀏覽器以不安全方式實作，進而允許攻擊者降低連線(E.g. POODLE 中的連線)。因此，建議完全停用這些通訊協定。


---

# 修補方式

1. 停用 SSL 2.0/3.0，改用 TLS 1.2(包含核准的加密套件)或更新版本。

## IIS

透過修改機碼方式，關閉 SSL。

1. 開啟註冊表(`regedit.exe`)，並至路徑 `\[HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders\\SCHANNEL\\Protocols\\SSL2.0\]`。SSL 3.0 路徑為 `\[HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders\\SCHANNEL\\Protocols\\SSL3.0\]`。
2. 在 SSL 2.0 資料夾點擊右鍵 -> 新增 -> 機碼，輸入 `Server`。
3. 在剛剛新增 Server 資料夾點擊右鍵 -> 新增 -> `DWORD(32位元)值`，輸入 `Enabled`。
4. 確認資料欄位是否為 `0x00000000(0)`，若否，請手動將值修改為 `0`。


---
