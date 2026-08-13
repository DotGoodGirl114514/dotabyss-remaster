# Dot Abyss Remaster

給一般玩家使用的完整安裝包，不需要事先安裝 BepInEx。

## 安裝

1. 關閉遊戲。
2. 下載 [`dotabyss-remaster-full.zip`](./dotabyss-remaster-full.zip)。
3. 找到包含遊戲 `.exe` 的資料夾。
4. 將 ZIP 內的所有內容直接解壓到該資料夾。
5. 確認 `winhttp.dll` 與遊戲 `.exe` 位於同一層，然後啟動遊戲。

第一次啟動會建立必要檔案，可能需要幾分鐘；完成後右上角會出現插件面板。

## 基本操作

- 插件預設啟用，可從右上角面板調整或關閉功能。
- `F6`：展開／收合右上角面板。
- `F5`：重設 DPS 統計。
- `F12`：展開／收合 DPS 面板。

## 移除

刪除遊戲目錄中的 `winhttp.dll`、`.doorstop_version`、`doorstop_config.ini`、`dotnet` 與 `BepInEx` 即可。

## 第三方元件

安裝包內含 [BepInEx 6.0.0-be.784（Windows x64 / IL2CPP）](https://builds.bepinex.dev/projects/bepinex_be)，依其 LGPL-2.1 授權散布；授權全文收錄於 ZIP 內的 `BEPINEX_LICENSE.txt`。
