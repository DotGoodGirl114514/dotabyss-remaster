# Dot Abyss Remaster

## 安裝

1. 關閉遊戲。
2. 到 [Releases](../../releases) 下載最新版的 `Source code (zip)`。
3. 解壓縮後，開啟最外層的版本資料夾。
4. 將裡面的所有檔案複製到包含遊戲 `.exe` 的資料夾。
5. 確認 `winhttp.dll` 與遊戲 `.exe` 位於同一層，然後啟動遊戲。

第一次啟動可能需要幾分鐘。成功載入後，右上角會出現插件面板。

## 基本操作

- 插件預設啟用，可從右上角面板調整或關閉功能。
- `F6`：展開／收合右上角面板。
- `F5`：重設 DPS 統計。
- `F12`：展開／收合 DPS 面板。

## Reroll 設定

設定檔位於 `BepInEx/plugins/AbyssSniff/reroll_config.json`。修改前請先關閉遊戲並備份檔案；文字與標點必須維持合法 JSON 格式。

- `enabled`：Reroll 總開關。
- `auto_play`：自動點擊開始、復歸、再挑戰等流程。
- `mode`：失敗時的處理模式；預設 `nether_reload` 用於深淵流程。
- `match_mode`：`any` 表示符合任一目標便保留，`all` 表示必須全部符合。
- `desired_drops`：通用掉落目標。可用 `content_type`、`content_id`、`min_rarity_level`、`min_amount` 與 `min_count` 篩選。
- `quest_drop_targets`：依 `quest_id` 指定單一關卡的掉落目標；會優先於通用條件。
- `nether_rules`：依深淵樓層範圍與樓層類型設定保留條件；第一條符合範圍的規則生效。
- `nether_*`：深淵路線、自動走圖、Code 選擇與稀有度門檻。
- `exploration_*`：探索關卡的稀有度門檻、失敗重試方式與等待時間。
- `disaster_*`、`chapter_disaster_*`、`event_disaster_*`：不同災厄關卡的目標與撤退重刷條件。
- `force_chain_*`：自動 Force Chain 的 Mana、人數、冷卻與名稱條件。
- 名稱結尾為 `_sec` 的欄位：相關動作的等待秒數；遇到載入較慢或操作過快時再提高。
- `comment`：只供閱讀，不影響判定。

設定檔已附一組預設規則。不確定欄位用途時，建議只改 `enabled`、目標掉落與各功能開關。

## 移除

刪除遊戲目錄中的 `winhttp.dll`、`.doorstop_version`、`doorstop_config.ini`、`dotnet` 與 `BepInEx`。

## 第三方元件

內含 [BepInEx 6.0.0-be.784（Windows x64 / IL2CPP）](https://builds.bepinex.dev/projects/bepinex_be)，依 LGPL-2.1 授權散布；授權全文見 `BEPINEX_LICENSE.txt`。
