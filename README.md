# Project Name

## 🚀 クイックスタート

### 1. 環境セットアップ

```bash
# uvを使用して依存関係をインストール
uv sync

# 開発ツールも含めてインストール
uv sync --group dev --group notebook
```

### 2. 開発環境の初期化

```bash
# pre-commitフックを設定
uv run pre-commit install

# Jupyter Labを起動
uv run jupyter lab
```

## 📁 プロジェクト構造

```
research-template/
├── configs/          # 設定ファイル（YAML, JSON等）
├── data/            # データファイル（Gitで管理されません）
│   ├── raw/         # 生データ
│   ├── processed/   # 前処理済みデータ
│   └── external/    # 外部データソース
├── docs/            # ドキュメント
├── results/         # 実験結果・出力ファイル（Gitで管理されません）
│   ├── figures/     # 図表
│   ├── models/      # 学習済みモデル
│   └── reports/     # レポート
├── scripts/         # 実行スクリプト
│   ├── data/        # データ処理スクリプト
│   ├── experiments/ # 実験実行スクリプト
│   └── utils/       # ユーティリティスクリプト
├── src/             # ソースコード
│   ├── data/        # データ処理モジュール
│   ├── models/      # モデル定義
│   ├── features/    # 特徴量エンジニアリング
│   └── visualization/ # 可視化
├── tests/           # テストコード
└── pyproject.toml   # プロジェクト設定
```

## 🛠️ 開発ツール

このテンプレートには以下の開発ツールが含まれています：

### コード品質
- **[Ruff](https://docs.astral.sh/ruff/)**: 高速なPythonリンター・フォーマッター
- **[Pyright](https://github.com/microsoft/pyright)**: 型チェッカー
- **[pre-commit](https://pre-commit.com/)**: コミット前の自動チェック

### テスト
- **[pytest](https://pytest.org/)**: テストフレームワーク
- **[pytest-cov](https://pytest-cov.readthedocs.io/)**: カバレッジ測定

### ノートブック
- **[JupyterLab](https://jupyterlab.readthedocs.io/)**: インタラクティブ開発環境
- **[nbstripout](https://github.com/kynan/nbstripout)**: ノートブック出力の自動削除

### テストの実行

```bash
# 全テストを実行
uv run pytest

# カバレッジ付きでテスト実行
uv run pytest --cov=src --cov-report=html
```

### コード品質チェック

```bash
# リンティング
uv run ruff check src/ tests/

# フォーマッティング
uv run ruff format src/ tests/

# 型チェック
uv run pyright src/
```

## 📝 ベストプラクティス

### コード組織
- 再利用可能なコードは`src/`に配置
- 一回限りのスクリプトは`scripts/`に配置
- 設定は`configs/`でYAMLファイルとして管理

### データ管理
- 生データは`data/raw/`に配置（変更しない）
- 前処理済みデータは`data/processed/`に配置
- 大きなデータファイルはGitで管理しない

### 実験管理
- 各実験に一意の名前/IDを付ける
- 実験設定を`configs/`で管理
- 結果は`results/`に保存

### バージョン管理
- 意味のあるコミットメッセージを書く
- ブランチを使って機能開発を分離
- プルリクエストでコードレビューを実施
