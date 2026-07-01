# システム設計

## 初期技術スタック

- 言語: Python
- DB: SQLite
- UI: CLI
- レポート: 静的HTML

## 推奨モジュール構成

- `finance_analysis/cli.py`: CLIエントリーポイント。
- `finance_analysis/config.py`: パスとデフォルト設定。
- `finance_analysis/csv_importer.py`: CSV読み込み、検証、正規化。
- `finance_analysis/db.py`: SQLite接続とスキーマ管理。
- `finance_analysis/models.py`: 型付きレコードまたはdataclass。
- `finance_analysis/analysis.py`: 集計とレポート用データ作成。
- `finance_analysis/report.py`: HTMLレンダリング。
- `templates/`: HTMLテンプレート。
- `tests/`: 匿名化したfixtureを使ったテスト。

## レイヤー分割

- CSV取り込み: 入力ファイルを読み、必須列検証と型変換を行う。
- DB保存: 取り込み済みファイル、取引明細、分類ルールを保存する。
- 分析: DBから集計用データを読み、月別やカテゴリ別に集計する。
- レポート生成: 分析結果をHTMLへレンダリングする。

## 初期データモデル案

### import_files

取り込み済みCSVファイルを管理する。

- id
- file_name
- file_path
- file_hash
- imported_at
- row_count

### transactions

Money Forwardの取引明細を保存する。

- id
- transaction_date
- description
- memo
- amount
- major_category
- minor_category
- account_name
- money_forward_id
- is_transfer
- is_excluded
- is_calculation_target
- custom_category
- custom_subcategory
- source_file_id
- source_row_number
- row_hash
- raw_data_json
- created_at
- updated_at

### category_rules

独自カテゴリや補正ルールを保存する。

- id
- rule_name
- match_field
- match_type
- match_value
- custom_category
- enabled
- created_at
- updated_at

## 想定コマンド

```bash
python -m finance_analysis import
python -m finance_analysis import data/csv/*.csv
python -m finance_analysis report --from 2026-01-01 --to 2026-12-31 --output reports/2026.html
python -m finance_analysis summary
```

