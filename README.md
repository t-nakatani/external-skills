# External Skills Catalog

他者が公開している agent skill / plugin を、出典を保ったまままとめるためのカタログです。

このリポジトリの管理者はスキルの著作者ではありません。各スキルの著作権・ライセンス・利用条件は、必ず個別の出典元を確認してください。

## 方針

- upstream の構成と内容をできるだけそのまま `vendor/` に保存する
- 取得元リポジトリ、対象パス、参照したリビジョンを `sources.yaml` に記録する
- upstream のライセンス表示を削除しない
- このカタログ固有の説明・分類・変換は、vendor 本体と分離する
- 更新時は差分と upstream の変更点を確認してから取り込む

## 登録済みソース

| ID | 出典 | 対象 | 状態 |
| --- | --- | --- | --- |
| `lassejlv-skills` | [lassejlv/skills](https://github.com/lassejlv/skills) | リポジトリ内の `skills/` | 取得元登録済み・ライセンス確認待ち・実体は未公開 |
| `cursor-pstack` | [cursor/plugins/tree/main/pstack](https://github.com/cursor/plugins/tree/main/pstack) | `pstack` プラグイン一式 | 取得元登録済み・MIT |

## ディレクトリ構成

```text
external-skills/
├── README.md       # このカタログの説明と運用方針
├── sources.yaml    # upstream と取得条件の台帳
├── ATTRIBUTIONS.md # upstream の著作者・ライセンス・公開可否
└── vendor/         # ライセンス確認済みupstreamのスナップショット
    └── cursor-pstack/
```

`vendor/` 配下の各ディレクトリは、どの upstream に対応するかが名前だけで分かるようにします。Cursor の `pstack` は単独スキルではなく、プラグイン設定・agents・skills を含むため、`skills/` だけを切り出さずプラグイン単位で保存します。ライセンスが確認できないソースは、出典だけを登録し、実体を公開しません。

## 利用上の注意

このリポジトリは upstream の代替・公式ミラーではありません。利用者は、各 upstream の最新情報とライセンスを確認してください。
