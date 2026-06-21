# EOCMEET 安全注意事項

## 系統定位

EOCMEET 是離線優先、區域網路優先的應急視訊會議系統，建議部署於 LAN、VPN、專線、臨時 Wi-Fi、行動路由器或衛星路由器內網。

## 不建議做法

- 不建議直接暴露於公開網際網路。
- 不建議在未設定 PIN、管理密碼、防火牆的情況下提供外部連線。
- 不建議把 runtime secret、log、db、附件或現場資料上傳到 GitHub。

## 發布包不得包含

```text
livekit_api_secret.txt
proxy_header_secret.txt
meeting_pin.txt
runtime.json
security_profile_selected.txt
security.log
*.log
*.db
*.sqlite
__pycache__/
*.pyc
_eocmeet_internal/data/
_eocmeet_internal/runtime/
_eocmeet_internal/logs/
_eocmeet_internal/uploads/
```

## 建議安全設定

1. 一般測試請選 PIN 保護模式。
2. 非必要時不要開放附件上傳。
3. 管理者密碼請使用強密碼。
4. 只允許可信任內網或 VPN 使用。
5. 使用前先確認電腦防火牆規則。
6. 發布前重新檢查 ZIP 是否包含敏感資料。
7. 正式勤務環境使用前，應完成實機測試與資安審查。

## 外網注意

如果因特殊需求要跨地點使用，建議透過 VPN、專線、Cloudflare Access、Zero Trust 或固定 IP 白名單方式控管，不建議裸露於公開網際網路。
