# Dot Abyss Remaster

完全免費發布，禁止商用，僅供技術學習及交流性質
<br>反饋及 Bug 提交請至 QQ: 1057775708
<br>支援 PC-X 版，一般版跟移動端暫無支援

## 安裝

1. 關閉遊戲與 DMM GAME PLAYER。
2. 到 [Releases](../../releases) 下載最新版的 `Source code (zip)`。
3. 解壓縮後，開啟最外層的版本資料夾。
4. 將資料夾內的所有檔案複製到遊戲目錄：

   ```text
   C:\Users\{{user}}\dotabyss_x_cl
   ```

   `{{user}}` 是目前登入 Windows 的使用者名稱。系統詢問是否合併資料夾或覆蓋檔案時，選擇允許。

5. 覆蓋完成後，確認以下檔案位於對應位置：

   ```text
   C:\Users\{{user}}\dotabyss_x_cl\ドットアビスX.exe
   C:\Users\{{user}}\dotabyss_x_cl\winhttp.dll
   C:\Users\{{user}}\dotabyss_x_cl\BepInEx\plugins\AbyssSniff\AbyssSniff.dll
   C:\Users\{{user}}\dotabyss_x_cl\BepInEx\plugins\AbyssSniff\reroll_config.json
   ```

6. 啟動遊戲。第一次啟動可能需要幾分鐘；成功載入後，右上角會出現插件面板。

### 覆蓋完成示意

`BepInEx`、`dotnet`、`winhttp.dll` 與 `ドットアビスX.exe` 應位於下圖所示的同一個遊戲根目錄：

![覆蓋完成後的遊戲目錄](assets/install-after-copy.png)

## Bug 修正

1. 負面狀態施加失敗時，不再清除已成功施加的負面狀態。
2. 修正戰鬥中連擊率提升 Buff 實質不生效。
3. 修正「漆黑之杖」的負面狀態提升 Buff 效果與說明不同，現在可以正常疊加。

## 角色修正

| 角色 | 修正內容 |
| :---: | --- |
| <img src="assets/character-laveria.png" alt="ラヴェリア" width="96"><br>**ラヴェリア** | **情熱紋章改為敵人被擊倒時賦予，不限定由自身擊倒。** |
| <img src="assets/character-christie.png" alt="クリスティ" width="96"><br>**クリスティ** | **ステラレコード重複賦予時，持續時間改為疊加而不是覆蓋。** |
| <img src="assets/character-film.png" alt="フィルム" width="96"><br>**フィルム** | **ノワール憑依重複賦予時，持續時間改為疊加而不是覆蓋。** |

三項角色修正預設開啟。遊戲中按 `F4` 可整體關閉／開啟；狀態會寫入 `reroll_config.json` 的 `character_fixes_enabled`，重開遊戲後仍會沿用。切換時畫面上方會短暫顯示提示。若在戰鬥中切換，已經建立的角色效果不會被強制重建，完整狀態以新一場戰鬥為準。

## 功能

1. **自動探索裝備 Reroll**
   依稀有度、出現 Rank 與裝備種類判斷探索掉落；不符合條件時自動進入失敗與再挑戰流程，直到出現指定裝備。

2. **自動災厄裝備 Reroll**
   支援一般災厄、章節災厄與活動災厄。掉落不符合設定時自動撤退並重新出擊。

3. **深淵自動化**

   - 自動尋路，優先選擇符合策略的樓層路線。
   - 自動判斷並取得 Abyss Code。
   - 自動 Reroll，依設定刷鑑定道具與金／紅裝備。
   - 修正啟動時的 Reroll 落地判斷：深淵進行中才開啟功能不再誤等「再開する」；從標題進入且沒有續戰時，也會在首頁載入完成後自動解除等待。
   - 可把新一輪深淵原生的 10F 起點替換為指定 checkpoint 樓層。

4. **藍寶石施放條件優化**
   可依 Mana、可參與人數、冷卻時間與藍寶石名稱設定自動施放條件，不再受遊戲原生 AUTO 的固定條件限制。預設支援 `情熱のマナクリスタル` 與新的 `衝撃のマナクリスタル`，名稱後方帶有 `【崩壊】`、`【虚空】` 等種類後綴也能辨識。

5. **詳盡 DPS 表**
   顯示角色總傷害、對災厄傷害、普攻、技能、Chain、追擊、召喚物、Mana 與連擊次數，並可依總傷害或 Boss 傷害排序。

6. **Boss 抗性展示**
   顯示各負面狀態的基礎抗性、蓄積抗性、目前總抗性、成功時增加量、實際衰減速度與最近一次施加判定。

## 功能預覽

### 自動化開關與探索掉落篩選

可直接在遊戲內切換總開關、深淵、探索、災厄與藍寶石自動化，並設定探索裝備的稀有度、出現 Rank、武器及防具種類。

![自動化開關與探索掉落篩選面板](assets/automation-filter-panel.png)

### Boss 異常抗性

即時顯示各負面狀態的基礎抗性、蓄積值、總抗性、衰減速度，以及最近一次施加的計算結果。

![Boss 異常抗性面板](assets/boss-resistance-overlay.png)

### 詳盡 DPS 表

依角色顯示總傷害、對災厄傷害、角色傷害，以及普攻、技能、Chain 與連擊次數等細項。

![詳盡 DPS 統計面板](assets/dps-overlay.png)

## 基本操作

- 插件預設啟用，可從右上角面板調整或關閉功能。
- `F4`：整體開啟／關閉三項角色修正，並寫回設定檔。
- `F6`：展開／收合右上角面板。
- `F5`：重設 DPS 統計。
- `F12`：展開／收合 DPS 面板。

## Reroll 設定

設定檔位於 `BepInEx/plugins/AbyssSniff/reroll_config.json`。插件只在啟動時讀取設定，因此修改前請先關閉遊戲並備份檔案，存檔後再重新啟動遊戲。

這是標準 JSON，不能加入 `//` 註解、不能漏掉逗號，也不能在最後一項後面多放逗號。需要備註時請使用現成的 `comment` 欄位；它不參與判定。

如果舊設定中的中文或日文是 `\u6DF1\u6DF5` 這類字樣，檔案並沒有損壞；這只是 JSON 的 Unicode escape，插件讀到的文字與原文完全相同。v1.3.2 起，按 `F4` 寫回角色修正開關時會保留可讀的中文／日文。

### 常用總開關

| 欄位 | 用途 |
| --- | --- |
| `enabled` | Reroll 與自動化總開關的初始值。 |
| `character_fixes_enabled` | ラヴェリア／クリスティ／フィルム三項角色修正；也可在遊戲中按 `F4` 一起切換。 |
| `auto_play` | 自動點擊開始、復歸、再挑戰等流程。 |
| `mode` | 深淵判定失敗後的處理模式；發布版預設使用 `nether_reload`。 |
| `console_log_enabled` | 是否在 BepInEx console 顯示判定與自動化狀態。 |
| `nether_autopath_enabled` | 深淵自動尋路。 |
| `nether_checkpoint_override_floor` | 新一輪深淵原生準備從 10F 開始時，改送指定 checkpoint 樓層；預設 `10` 表示不替換。 |
| `nether_autobuff_mode` | Abyss Code：`on` 自動選、`log` 只判定不點擊、`off` 關閉。 |
| `force_chain_auto_enabled` | 自動施放 Force Chain 的初始值。 |

名稱結尾為 `_sec` 的欄位都是相關動作的等待秒數；只有遇到載入較慢或操作過快時才需要提高。

### 深淵初始樓層替換

`nether_checkpoint_override_floor` 只會在遊戲原生準備送出 `10F` 的新一輪深淵請求時生效；續玩既有進度或遊戲要求的其他樓層不會被改寫。

- `10`：預設值，完全沿用遊戲原生行為。
- `20`～`120`：可指定的 checkpoint 樓層，必須是 `10` 的倍數。
- 其他數字：視為 `10`，不替換請求。

第一次以非 `10` 的值建立新一輪深淵時，遊戲可能停在載入畫面。這時關閉並重新啟動遊戲，再進入深淵，就會從指定樓層開始。請在改設定前先結束目前的深淵進度；這個選項只替換新一輪的起始樓層，不會在進行中的地圖內直接跳樓。

### 深淵 Reroll 落地判斷

v1.4.0 起，只有確實經過標題／GAME START 或插件主動返回標題時，才會暫停掉落判定並等待續戰流程。若在已進行中的深淵才開啟 Reroll，下一個正常戰鬥會直接評估，不會因為沒有關卡 cache 而永久停在 `WaitingForResume`。

從標題進入但沒有進行中的深淵時，首頁載入完成且未出現「再開する／復帰」彈窗後，插件會自動解除續戰等待；若彈窗稍晚出現，仍會等到實際點擊續戰後才評估，避免把載入期間的 cached response 當成新的掉落結果。這項修正不需要新增設定。

### 藍水晶自動施放

`force_chain_allow_names` 是可自動施放的水晶名稱白名單，使用子字串比對。v1.4.0 的預設值為：

```json
"force_chain_allow_names": [
  "情熱のマナクリスタル",
  "衝撃のマナクリスタル"
]
```

因此 `情熱のマナクリスタル【崩壊】`、`衝撃のマナクリスタル【虚空】` 等帶後綴名稱都會命中。已有自訂 `force_chain_allow_names` 的舊設定不會被強制改寫；需要新水晶時，請自行把 `衝撃のマナクリスタル` 加入陣列。

### 一般掉落篩選

`desired_drops` 是通用掉落目標，`quest_drop_targets` 則用 `quest_id` 鎖定單一關卡，而且優先於通用條件。`match_mode: "any"` 表示任一目標命中便保留，`"all"` 表示每個目標都必須命中。

| 篩選欄位 | 用途 |
| --- | --- |
| `content_type` | 限定掉落類型。不同模式的 preview 可能回報不同值；有明確 ID 時優先用 `content_id`。 |
| `content_id` | 精確指定一種掉落。 |
| `min_rarity_level` | 最低稀有度；目前 `3` 為金、`4` 為紅。 |
| `min_amount` | 單筆掉落的最低數量。 |
| `min_count` | 至少要有幾筆符合此篩選；省略時為 `1`。 |
| `comment` | 人類可讀說明，不影響判定。 |

例如只保留指定關卡的「聖者のマント」：

```json
{
  "quest_id": 6203,
  "quest_type": 3,
  "comment": "只刷聖者のマント",
  "desired_drops": [
    {
      "content_id": 22010430,
      "min_count": 1,
      "comment": "聖者のマント レジェンダリー"
    }
  ]
}
```

把這個物件放進 `quest_drop_targets` 陣列即可。這裡的 `quest_id` 是 start-battle response 裡的戰鬥 ID，不是章節或區域編號。

### 深淵 `nether_rules`

`nether_rules` 由上往下尋找，**第一條**同時符合樓層範圍與 `floor_types` 的規則生效，因此較窄、較特殊的範圍要放前面。

| 欄位 | 用途 |
| --- | --- |
| `floor_min` / `floor_max` | 規則涵蓋的樓層，包含上下界。 |
| `floor_types` | `1`＝戦闘、`2`＝ボス、`3`＝強敵；陣列內任一類型皆可命中。 |
| `pass_gold_count` | 金裝數量達標便 PASS；`0` 表示停用這條條件。 |
| `pass_red_count` | 紅裝數量達標便 PASS；`0` 表示停用這條條件。 |
| `pass_content_ids` | 任一指定 `content_id` 出現便 PASS，例如 `110001` 是鑑定道具。 |
| `pass_requirements` | 精確的 ID 組合條件，適合指定武器種類的黃袋。多個 requirement 之間是 OR。 |
| `reroll_attempt_cap` | 重刷到此次數後強制 PASS，避免死循環；`0` 表示無上限。 |
| `equip_content_type` | 只限制金／紅數量統計，不影響 `pass_content_ids` 或 `pass_requirements` 的 ID 比對。 |

同一條 `nether_rule` 裡，金裝數、紅裝數、`pass_content_ids`、各個 `pass_requirements` 與次數上限之間都是 **OR**：任一條件達標就保留該場。

`pass_requirements` 的欄位語意如下：

- `content_ids`：可計數的 ID 清單。
- `min_total`：清單內掉落合計至少幾個；省略時為 `1`。
- `require_any_of`：除了 `min_total` 外，還必須至少包含這個清單中的一種；空陣列表示沒有必含項目。
- `count_amount`：`true` 依掉落 `amount` 加總；`false` 則每筆掉落只算一次。省略時為 `true`。

`pass_requirements` **不另外判斷 `rarity_level`**，只精確比對 `content_id`。黃袋的武器種類、Rank 與稀有度已包含在各自的固定 ID 中；例如 `210234`、`210235` 在 master data 中分別就是 LE（稀有度 4）的 LV5 弓袋與銃袋，因此指定這兩個 ID 本身就已限定「LV5 紅裝」。若改用 `pass_red_count`，則會接受所有達到紅裝門檻的裝備種類，不適合只刷指定武器。

例如 91–100F 只保留 LV5 紅裝黃袋的弓或銃，可把該規則的 `pass_requirements` 改成：

```json
"pass_requirements": [
  {
    "comment": "LE ナゾの袋ランク5：弓或銃",
    "content_ids": [210234, 210235],
    "require_any_of": [],
    "min_total": 1
  }
]
```

若希望一定要有銃，而且弓／銃合計至少兩袋，可改成 `content_ids: [210234, 210235]`、`require_any_of: [210235]`、`min_total: 2`。

### LV5 金／紅裝黃袋 ID

以下為 master data 已核對的 SSR（稀有度 3／金色）與 LE（稀有度 4／紅色）LV5 黃袋 ID。兩個樓層帶使用不同系列的袋子，ID 不可混用。

> **樓層邊界：**發布版預設規則中，90F 仍屬 `41–90`；一般 `ナゾの袋ランク5` 專用規則是 **91–100F**，不是從 90F 開始。

#### 91–100F `ナゾの袋ランク5`

| 武器種類 | SSR／稀有度 3（金色） | LE／稀有度 4（紅色） |
| :---: | ---: | ---: |
| 片手剣 | `210221` | `210231` |
| 両手剣 | `210222` | `210232` |
| 拳 | `210223` | `210233` |
| 弓 | `210224` | `210234` |
| 銃 | `210225` | `210235` |
| 杖 | `210226` | `210236` |
| 魔導書 | `210227` | `210237` |
| ピッケル | `210228` | `210238` |

#### 101–130F `浸食ナゾの袋ランク5`

| 武器種類 | SSR／稀有度 3（金色） | LE／稀有度 4（紅色） |
| :---: | ---: | ---: |
| 片手剣 | `210321` | `210331` |
| 両手剣 | `210322` | `210332` |
| 拳 | `210323` | `210333` |
| 弓 | `210324` | `210334` |
| 銃 | `210325` | `210335` |
| 杖 | `210326` | `210336` |
| 魔導書 | `210327` | `210337` |
| ピッケル | `210328` | `210338` |

若要同時接受 91–100F 的金／紅弓與銃，`content_ids` 可填 `[210224, 210225, 210234, 210235]`；101–130F 則填 `[210324, 210325, 210334, 210335]`。

發布版內附一組可直接使用的預設規則。若只想換要刷的武器種類，通常只需修改相應樓層規則中 `pass_requirements[].content_ids`；不要改動其他流程與等待時間。

## 移除

若沒有安裝其他 BepInEx 插件，可刪除遊戲目錄中的 `winhttp.dll`、`.doorstop_version`、`doorstop_config.ini`、`dotnet` 與 `BepInEx`。

若還有其他 BepInEx 插件，只刪除 `BepInEx/plugins/AbyssSniff`。

## 第三方元件

內含 [BepInEx 6.0.0-be.784（Windows x64 / IL2CPP）](https://builds.bepinex.dev/projects/bepinex_be)，依 LGPL-2.1 授權散布；授權全文見 `BEPINEX_LICENSE.txt`。
