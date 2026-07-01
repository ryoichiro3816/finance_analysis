# ドキュメント目次

このディレクトリは、AIエージェントと開発者が同じ前提で作業するための詳細ドキュメントをまとめる場所です。

詳細な目次は `index.md` を参照してください。

## 読む順番

1. `index.md`
2. `overview/index.md`
3. `requirements/index.md`
4. `data/index.md`
5. `architecture/index.md`
6. `implementation/index.md`
7. `operations/index.md`

## ディレクトリ構成

- `overview/`: プロジェクト概要と現在の状態。
- `requirements/`: 機能要件、非機能要件、未決事項。
- `data/`: CSV仕様、保存方針、データ取り扱い。
- `architecture/`: システム設計、モジュール構成、データモデル。
- `architecture/decisions/`: 技術選定や設計判断の記録。
- `implementation/`: 実装順序、受け入れ条件、将来の作業メモ。
- `operations/`: 個人データ保護、運用上の注意。

## 正本の扱い

- AI向け入口はルートの `AGENTS.md`。
- 詳細な仕様は `docs/` 配下を正本とする。
- ルートの `requirements.md` は初期要件定義の履歴として残す。
- 今後、要件を更新する場合は `docs/requirements/product-requirements.md` を優先して更新する。
