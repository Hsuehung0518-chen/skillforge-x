# SkillForge X v20.1｜安全治理版

可直接部署至 GitHub Pages 或 Netlify 的純前端版本，不需要建置、不使用外部 CDN，也不會自動上傳資料。

## 本機測試

```bash
python3 -m http.server 8080
```

開啟 `http://localhost:8080`。請勿直接用 `file://` 作為正式驗收環境。

## GitHub

1. 建立新 repository，例如 `skillforge-x`。
2. 將本資料夾全部內容推送到 `main`。
3. 若用 GitHub Pages：Settings → Pages → Deploy from branch → `main` / `(root)`。

## Netlify（建議）

1. Netlify 選 Add new site → Import an existing project。
2. 連接上述 GitHub repository。
3. Publish directory 填 `.`；Build command 留空。
4. 部署後用手機網址執行 `TEST_CHECKLIST.md`。

## 資料與安全

- 歸檔只存在目前網域的 localStorage。
- JSON 格式包含 `app`、`schemaVersion` 與 `items`，匯入限制 1MB／100 筆並逐欄檢查。
- 使用者內容用 `textContent` 呈現，避免本機儲存型 HTML 注入。
- 刪除、清空與覆蓋匯入均先確認；刪除與清空提供本次工作階段復原點。
- CSP 阻擋網路連線與第三方資源；不要求相機、麥克風、定位或付款權限。

注意：此版本的風險燈號是關鍵詞初篩，不是價格、平台條款、收益或外部事實的查證結果。
