# Z001 備考資料庫

2026 港澳台研究生招生考試 · 綜合能力（一）中華文化板塊備考資料

## 部署到 Render 的步驟

### 第一步：在 GitHub 建立新的 Repository

1. 打開 [github.com](https://github.com) 登入
2. 點右上角 **+** → **New repository**
3. 填寫：
   - Repository name: `z001-study`（或任何你喜歡的名字）
   - 選 **Public**
   - **不要**勾選 Add a README（我們已經有了）
4. 點 **Create repository**

### 第二步：把檔案推上 GitHub

在你的電腦終端機（Terminal / 命令提示字元）執行：

```bash
# 進入專案資料夾（把路徑換成你下載的位置）
cd z001-study-site

# 初始化 Git
git init
git add .
git commit -m "first commit"

# 連結到你的 GitHub repo（把 YOUR_USERNAME 換成你的帳號）
git remote add origin https://github.com/YOUR_USERNAME/z001-study.git
git branch -M main
git push -u origin main
```

### 第三步：在 Render 建立新的 Static Site

1. 打開 [render.com](https://render.com) 登入
2. 點 **New** → **Static Site**
3. 連結你的 GitHub，選擇 `z001-study` 這個 repo
4. 填寫設定：
   - **Name**: `z001-study`（這會變成網址的一部分）
   - **Branch**: `main`
   - **Publish Directory**: `.`（只要打一個點）
5. 點 **Create Static Site**

等幾十秒部署完成，你會得到一個網址，像是：
`https://z001-study.onrender.com`

### 這樣就和班網完全分開了！

- 班網 = 一個 Render 服務（連結班網的 GitHub repo）
- 備考資料 = 另一個 Render 服務（連結這個新的 GitHub repo）

兩者互不影響，各自獨立部署。

## 檔案結構

```
z001-study-site/
├── index.html              ← 首頁（入口）
├── pages/
│   ├── knowledge-base.html ← 知識庫（按板塊分類）
│   ├── matrix.html         ← 知識矩陣（朝代×板塊）
│   └── quick-ref.html      ← 合稱鼻祖速查手冊
└── README.md               ← 這個說明檔
```

## 更新內容

之後要新增或修改頁面，只需要：

1. 修改檔案
2. `git add . && git commit -m "更新內容" && git push`
3. Render 會自動重新部署（通常 30 秒內完成）
