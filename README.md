<!-- ffxiv-tc-port 繁體中文說明開始 -->
# EXDSchema(台服 fork)

遊戲 Excel（EXD）資料表的欄位定義：每張表一個 `<表名>.yml`，寫明各欄位的名稱與型別（上游 [xivdev/EXDSchema](https://github.com/xivdev/EXDSchema)）。這條分支 `ver/2025.07.30.0000.0000` 對應全球版 7.3 的資料結構，台服 EXD 的結構與它相同。

## 台服 fork 的目的

- 給台服 EXD 匯出工具 [xiv-data-oxidizer](https://github.com/ffxiv-tc-port/xiv-data-oxidizer) 當欄位名稱來源：它讀台服 sqpack，依這裡的定義把每張表匯出成有欄名的 CSV。
- schema 與遊戲資料對不上時，匯出結果會**靜默錯位**（欄名套到別的欄），不會報錯。

## 與上游的差異

- 移除上游的 `dispatch.yml` 工作流程（每次 push 都會觸發，並帶動上游的驗證流程）。schema 內容與上游相同。
- xiv-data-oxidizer 釘的是上游原本的版本，不含上面那顆移除 CI 的 commit。
- xiv-data-oxidizer 只依表名開啟 `<表名>.yml`，這份 README 不會被當成 schema 讀取。

## 誰在用它

- [xiv-data-oxidizer](https://github.com/ffxiv-tc-port/xiv-data-oxidizer)：子模組 `schemas`。

<!-- ffxiv-tc-port 繁體中文說明結束 -->
