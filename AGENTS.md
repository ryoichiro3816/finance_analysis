# AGENTS.md

このリポジトリは、Money ForwardからダウンロードしたCSVをローカルDBに蓄積し、独自の視点で分析したHTMLレポートを生成するための個人向け家計分析ツールです。

AIエージェントは、このファイルを入口として読み、詳細は `docs/` 配下の該当ドキュメントを参照してください。

## アプリ概要

- 入力: Money Forwardの「収入・支出詳細」CSV
- CSV原本置き場: `data/csv/`
- DB置き場: `data/db/`
- レポート出力先: `reports/`
- 初期実装方針: Python CLI + SQLite + 静的HTML
- 標準分析対象: `計算対象=1` かつ `振替=0`
- 振替・計算対象外の明細: DBには保存するが、標準収支レポートからは除外する

## docs目次

- `docs/index.md`: ドキュメント全体の目次
- `docs/overview/index.md`: プロジェクト概要の目次
- `docs/requirements/index.md`: 要件ドキュメントの目次
- `docs/data/index.md`: データ仕様と保存方針の目次
- `docs/architecture/index.md`: 設計ドキュメントの目次
- `docs/implementation/index.md`: 実装チェックリストの目次
- `docs/operations/index.md`: 運用・安全ルールの目次

## 作業前の読み方

1. まず `docs/index.md` を読む。
2. 要件確認が必要なら `docs/requirements/index.md` を読む。
3. CSV取り込みに触るなら `docs/data/index.md` を読む。
4. DBやモジュール構成に触るなら `docs/architecture/index.md` を読む。
5. 実装作業を始める前に `docs/implementation/index.md` を確認する。
6. 実データを扱う前に `docs/operations/index.md` を確認する。
