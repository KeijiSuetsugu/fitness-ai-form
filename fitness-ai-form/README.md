# AIフィットネス診断 & 姿勢チェック（Streamlit）

個人トレーナー向けのAI診断フォーム。  
- 栄養・運動の自動提案（BMR/TDEE/PFC）
- 食事テンプレ自動生成
- AI姿勢チェック（MediaPipe）
- 顧客レポート（.docx）出力
- SQLite保存、CSV/Excelエクスポート
- LINEステップ配信用テンプレ自動生成

## 使い方（ローカル）
1. Python 3.10+ 推奨
2. （任意）仮想環境を作成して有効化
3. 依存をインストール：
   ```bash
   pip install -r requirements.txt
   ```
4. アプリ起動：
   ```bash
   streamlit run app.py
   ```
5. ブラウザで `http://localhost:8501` を開く

## GitHub へのアップ
1. GitHubで新規リポジトリを作成（例：`fitness-ai-form`）。**Public** 推奨。
2. 手元のフォルダに以下3ファイルを保存：`app.py` / `requirements.txt` / `README.md`
3. GitHubのWeb画面で「Add file → Upload files」→ 3ファイルをドラッグ&ドロップ → Commit

**Repository とは？**  
- 例：アカウント名が `next-end`、リポジトリ名が `fitness-ai-form` の場合、  
  Repository 入力は **`next-end/fitness-ai-form`**（所有者/リポジトリ名）。

## Streamlit Cloud デプロイ（無料枠）
1. `https://streamlit.io/cloud` へアクセス → GitHubでログイン
2. 「New app」→ 入力：
   - **Repository**：`オーナー名/リポジトリ名`（例：`next-end/fitness-ai-form`）
   - **Branch**：`main`
   - **Main file path**：**`app.py`**
3. 「Deploy」をクリック → 数十秒で `https://xxxx.streamlit.app` が発行

### よくあるエラー
- **「このリポジトリは存在しません」**：
  - 入力が `所有者/リポジトリ名` 形式か確認（例：`next-end/fitness-ai-form`）
  - リポジトリの公開設定が **Public** か確認
  - Branch 名が `main` と一致しているか確認
- **依存のインストール失敗**：
  - `requirements.txt` をそのまま使う
  - Cloudで「Rerun/Restart」を実施
- **MediaPipe失敗**：
  - 環境により稀に失敗しても、アプリ自体は動作（姿勢解析は自動無効化）。

## データ保存
- 既定では `data.db`（SQLite）に保存。
- 無料枠では再デプロイ/スリープで初期化される可能性あり。永続化が必要なら Supabase / Neon 等へ移行。

## ライセンス
個人/商用プロジェクトで自由に利用可（自己責任）。
