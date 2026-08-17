# Dot Abyss Remaster

《ドットアビスX》PC-X 版的免費玩家插件，提供掉落 Reroll、深淵自動化、戰鬥統計與多項遊戲修正。禁止商用，僅供技術學習及交流。

- 反饋及 Bug 提交：QQ `1057775708`
- 支援：PC-X 版
- 暫不支援：一般版、移動端

## 主要功能

- **掉落 Reroll**：可依稀有度、Rank、裝備種類或指定掉落篩選結果，不符合時自動重試。
- **深淵自動化**：自動尋路、選擇 Abyss Code，並依樓層規則 Reroll 鑑定道具與金／紅裝備。
- **災厄自動化**：支援一般災厄、章節災厄與活動災厄，不符合目標時自動撤退重打。
- **藍寶石自動施放**：可依 Mana、參與人數、冷卻時間與水晶名稱決定施放時機。
- **隊伍水晶拆卸**：進入水晶裝備頁面，點選已裝備的水晶；出現提示後按照提示按下確認即可卸除，回到主編成畫面後再按「登録」保存。
- **戰鬥資訊**：提供角色 DPS 細項與 Boss 負面狀態抗性。
- **更新通知**：啟動遊戲時會查詢本專案的最新 GitHub Release；若本地版本較舊，會顯示新功能摘要與 Release 連結，每個新版本只提示一次。
- **Bug 修正**：修正部分 Buff、負面狀態與探索活動任務提示的異常行為。
- **災厄防禦塔自動操作**：Boss 或有效目標進入範圍後，攻擊塔與補血塔會自動運行，不再占用輔助角色。
- **體驗優化**：調整角色技能與易傷疊加效果，可隨時開啟或關閉。

**畫面上方的掉落 Filter 只適用於主線／活動關卡／探索；深淵與災厄的掉落條件必須在 `reroll_config.json` 調整。**

## 功能預覽

### 自動化與掉落 Filter

可在遊戲內切換自動化功能，並設定主線、活動關卡與探索的掉落條件。

![自動化開關與掉落篩選面板](assets/automation-filter-panel.png)

### 探索活動任務紅點

探索活動任務有已完成、尚未領取的獎勵時，活動任務按鈕會顯示紅點；完成新任務或領取獎勵後會自動更新。

![探索活動任務可領取獎勵紅點](assets/exploration-event-mission-badge.png)

### Boss 異常抗性

![Boss 異常抗性面板](assets/boss-resistance-overlay.png)

### DPS 統計

![詳盡 DPS 統計面板](assets/dps-overlay.png)

## 安裝

1. 關閉遊戲與 DMM GAME PLAYER。
2. 到 [Releases](../../releases) 下載最新版的 `Source code (zip)` 並解壓縮。
3. 將版本資料夾內的所有檔案複製到遊戲目錄：

   ```text
   C:\Users\{{user}}\dotabyss_x_cl
   ```

   `{{user}}` 是目前登入 Windows 的使用者名稱；系統詢問是否合併資料夾或覆蓋檔案時，請允許。

4. 啟動遊戲。第一次啟動可能需要幾分鐘；成功載入後，右上角會出現插件面板。

版本檢查無法連線時會靜默跳過，不會影響遊戲啟動或自動化功能。

`BepInEx`、`dotnet`、`winhttp.dll` 與 `ドットアビスX.exe` 應位於同一個遊戲根目錄：

![覆蓋完成後的遊戲目錄](assets/install-after-copy.png)

## 基本操作

- `F4`：整體開啟／關閉體驗優化；設定會自動保存。
- `F6`：展開／收合右上角面板。
- `F5`：重設 DPS 統計。
- `F12`：展開／收合 DPS 面板。

右上角的「Code 紫優先」預設為 OFF，預設侵蝕門檻為 `50`；開啟後會在門檻前最優先拿紫，
適合在短樓層快速刷 Code 紫點數。可搭配「深淵跳樓層入場」從 100 以上高樓層開始，
在侵蝕度不會滿百的情況下速刷。開關狀態會保存，重新啟動遊戲後沿用。

## Bug 修正

- 修正完成一輪深淵後重新進場時，深淵入場按鈕會被誤認為標題畫面的 `START`，導致後續掉落判定被當成 cached auto-fetch 而跳過 reroll 的問題。
- 修正探索活動任務完成後沒有紅點提示的問題；有可領取獎勵時會顯示紅點，戰鬥完成或領取獎勵後會自動更新。
- 負面狀態施加失敗時，不再清除已成功施加的負面狀態。
- 修正戰鬥中連擊率提升 Buff 實質不生效。
- 修正「漆黑之杖」的負面狀態提升 Buff 效果與說明不同，現在可以正常疊加。
- 修正 LE「深蝕のツルハシ」的開場情熱效果：現在只會對火／水／土屬性角色生效，不再覆蓋光／闇／無屬性角色原有的衝擊紋章。

Bug 修正會隨插件啟用，不受 `F4` 影響。

## 體驗優化

- 易傷效果可正常疊加，不會互相覆蓋。
- 災厄戰中原本需要輔助角色操作的防禦塔會自動運行；輔助角色不會被固定在塔前，可正常行動、發動被動技能與使用 FC，塔的飛彈、傷害及補血效果仍會正常生效。

| 角色 | 體驗優化內容 |
| :---: | --- |
| <img src="assets/character-laveria.png" alt="ラヴェリア" width="96"><br>**ラヴェリア** | 情熱紋章改為敵人被擊倒時賦予，不限定由自身擊倒。 |
| <img src="assets/character-christie.png" alt="クリスティ" width="96"><br>**クリスティ** | ステラレコード重複賦予時，持續時間改為疊加而不是覆蓋。 |
| <img src="assets/character-film.png" alt="フィルム" width="96"><br>**フィルム** | ノワール憑依重複賦予時，持續時間改為疊加而不是覆蓋。 |

體驗優化預設開啟，可按 `F4` 一起切換。若在戰鬥中切換，完整效果會從下一場戰鬥開始套用。

## 常用設定

設定檔位於 `BepInEx/plugins/AbyssSniff/reroll_config.json`。插件只在啟動時讀取設定，因此請先關閉遊戲、備份檔案，修改後再重新啟動。

這是標準 JSON：不能加入 `//` 註解、漏掉逗號或在最後一項後加逗號。`comment` 只供閱讀，不影響判定。

### 常用開關

| 欄位 | 用途 |
| --- | --- |
| `enabled` | Reroll 與自動化總開關的初始值。 |
| `auto_play` | 自動點擊開始、復歸、再挑戰等流程。 |
| `character_fixes_enabled` | 體驗優化總開關；也可按 `F4` 切換。 |
| `nether_autopath_enabled` | 深淵自動尋路。 |
| `nether_autobuff_mode` | Abyss Code：`on` 自動選、`log` 只顯示判定、`off` 關閉。 |
| `nether_buff_purple_first_until_erosion` | 「Code 紫優先」的侵蝕門檻，預設 `50`；門檻前最優先拿紫。 |
| `nether_checkpoint_override_floor` | 深淵跳樓層入場可設為 `10、20、…、120`；其他數值會自動使用 `10`。要使用 `20`～`120`，需先以原生流程正常進場一次，讓遊戲載入深淵資料。 |
| `force_chain_allow_names` | 允許自動施放的藍水晶名稱。 |

名稱以 `_sec` 結尾的欄位是等待秒數。只有載入較慢或自動操作過快時，才需要調高。

### 情境一：調整災厄目標

- `disaster_desired_drops`：一般災厄。
- `chapter_disaster_pass_content_ids`：章節災厄。
- `event_disaster_desired_drops`：活動災厄。

一般與活動災厄可用 `content_id` 指定掉落，並以 `min_count` 設定最低數量：

```json
"disaster_desired_drops": [
  {
    "content_id": 37010440,
    "min_count": 1,
    "comment": "目標掉落"
  }
]
```

### 情境二：調整深淵 Reroll

深淵使用 `nether_rules`。規則由上往下比對，第一條符合樓層與戰鬥類型的規則生效，所以範圍較特殊的規則應放在前面。

常用欄位：

- `floor_min`／`floor_max`：適用樓層。
- `floor_types`：`1` 戰鬥、`2` Boss、`3` 強敵。
- `pass_gold_count`／`pass_red_count`：至少出現幾件金／紅裝備。
- `pass_content_ids`：出現任一指定掉落 ID 即保留；`110001` 為鑑定道具。
- `pass_requirements`：指定裝備或黃袋 ID 組合。
- `reroll_attempt_cap`：最多重刷次數；`0` 表示無上限。

同一條規則中的保留條件是 **OR**，任一項達標就會保留該場。例如 41～90F 的一般戰鬥，出現一件金裝、一件紅裝或鑑定道具皆可保留：

```json
{
  "comment": "41-90F 一般戰鬥",
  "floor_min": 41,
  "floor_max": 90,
  "floor_types": [1],
  "pass_gold_count": 1,
  "pass_red_count": 1,
  "pass_content_ids": [110001],
  "reroll_attempt_cap": 100
}
```

發布版已附可直接使用的規則。若只想更換目標武器，通常只需修改相應樓層的 `pass_requirements[].content_ids`。

#### LV5 金／紅裝袋子 ID

將想要的袋子 ID 填入 `pass_requirements[].content_ids`。91–100F 使用 `ナゾの袋ランク5`，101–130F 使用 `浸食ナゾの袋ランク5`，兩組 ID 不可混用。

> 90F 仍屬於 41–90F；`ナゾの袋ランク5` 從 91F 開始。

| 武器種類 | 91–100F 金 | 91–100F 紅 | 101–130F 金 | 101–130F 紅 |
| :---: | ---: | ---: | ---: | ---: |
| 片手剣 | `210221` | `210231` | `210321` | `210331` |
| 両手剣 | `210222` | `210232` | `210322` | `210332` |
| 拳 | `210223` | `210233` | `210323` | `210333` |
| 弓 | `210224` | `210234` | `210324` | `210334` |
| 銃 | `210225` | `210235` | `210325` | `210335` |
| 杖 | `210226` | `210236` | `210326` | `210336` |
| 魔導書 | `210227` | `210237` | `210327` | `210337` |
| ピッケル | `210228` | `210238` | `210328` | `210338` |

### 情境三：調整藍水晶白名單

`force_chain_allow_names` 使用子字串比對，因此帶有 `【崩壊】`、`【虚空】` 等後綴的同名水晶也會命中：

```json
"force_chain_allow_names": [
  "情熱のマナクリスタル",
  "衝撃のマナクリスタル"
]
```

## 移除

若沒有其他 BepInEx 插件，可刪除遊戲目錄中的 `winhttp.dll`、`.doorstop_version`、`doorstop_config.ini`、`dotnet` 與 `BepInEx`。

若仍有其他 BepInEx 插件，只刪除 `BepInEx/plugins/AbyssSniff`。

## 第三方元件

內含 [BepInEx 6.0.0-be.784（Windows x64 / IL2CPP）](https://builds.bepinex.dev/projects/bepinex_be)，依 LGPL-2.1 授權散布；授權全文見 `BEPINEX_LICENSE.txt`。
