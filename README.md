# Dot Abyss Remaster Plugin

「ドットアビスX」用的 BepInEx 6 IL2CPP 插件發布包。此 repository 只包含已編譯 DLL、預設設定與安裝包，不包含原始碼、PDB、開發 log 或任何發布者帳號資料。

## 安裝

前提：遊戲已安裝可正常載入的 BepInEx 6 IL2CPP。

1. 下載 [`dotabyss-remaster.zip`](./dotabyss-remaster.zip)。
2. 關閉遊戲。
3. 將 ZIP 內容直接解壓到遊戲根目錄，讓檔案位於：
   `BepInEx\plugins\AbyssSniff\AbyssSniff.dll`
4. 啟動遊戲。

內附設定預設啟用插件與自動操作，磁碟封包記錄預設關閉。右上角面板可切換總開關、深淵、探索、災厄與水晶功能；F6 收合面板。

## 常用按鍵

- F5：清空 DPS 統計
- F6：收合／展開右上角面板
- F10：輸出 DPS 統計
- F11：切換磁碟 log／封包 dump（預設關閉）
- F12：切換 DPS 統計與面板
- Shift+F12：只切換 DPS 面板顯示

## 本機資料

插件產生的狀態、log、marker 與 dump 統一放在：
`BepInEx\plugins\AbyssSniff\data`

請勿公開分享 `data` 目錄；開啟 F11 後產生的封包 dump 可能含使用者自己的遊戲連線資料。

## 完整性

`AbyssSniff.dll` SHA-256：
`7E7313CB2800C5007BBDC6B01EEEC8D581E290D23F0728FC2C13F3196E3119CD`
