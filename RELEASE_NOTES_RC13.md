# EOCMEET RC13 Security QA Edition - Release Notes

本版本為 **Release Candidate**，建議用於公開下載測試、區域網路 LAN 使用、VPN 內部使用、災害演練與教育訓練。

## 版本定位

EOCMEET RC13 是一套離線優先、區域網路優先的應急視訊會議系統。GitHub 版本提供下載使用，不代表將服務直接架設於公開網際網路。

## RC13 重點修正

- 統一版本標示為 RC13 Security QA Edition。
- 管理頁 HTML 入口加上管理者 Session 檢查，不只保護 API。
- Session Cookie 改用 `__Host-` 前綴，並保留舊 Cookie 相容清理。
- 聊天、附件、加入、離開訊息補上 `identity`，避免自己事件被誤算未讀。
- 加入 / 離開 toast 只對新事件顯示，避免首次載入舊紀錄連續跳提示。
- 修正設定頁 IP 顯示，避免使用 `innerHTML`。
- 清除前端已不存在的 `fullscreenBtn`、`mobileFullscreenBtn`、`pinnedArea` 參照。
- 重新產生 `SHA256SUMS`、`SBOM` 與 `component_hashes.json`。

## 安全說明

發布包不應包含：

- `livekit_api_secret.txt`
- `proxy_header_secret.txt`
- `meeting_pin.txt`
- `runtime.json`
- `security_profile_selected.txt`
- `security.log`
- `__pycache__ / *.pyc`

## SHA256

```text
8a3c1c8c81a686f0a96512a3a62f6e3cf6dabd94517f179302308297a64b353e
```

## 已知限制

- 此版本仍屬 RC，不建議直接標示為 Stable。
- 尚建議進行手機實機、多人大量進出、螢幕分享後恢復視訊、伺服器端麥克風輸出與斷線重連測試。
- 不建議直接暴露於公開網際網路。

## 建議使用方式

- 區域網路 LAN
- VPN
- 臨時 Wi-Fi
- 行動路由器內網
- 衛星路由器內網
- 災害現場或指揮所內網
