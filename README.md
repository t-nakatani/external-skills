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
| `keitakn-explain-visually` | [keitakn/engineering-skills](https://github.com/keitakn/engineering-skills/tree/main/.claude/skills/explain-visually) | `explain-visually` スキル一式 | 取得元登録済み・MIT |

### explain-visually

長い設計文書・Pull Request・Issueを、図と短い文を組み合わせた解説HTMLに整理するスキルです。設計判断に識別子を付け、項目を指定して深掘りできます。

- スキル本体: [`SKILL.md`](vendor/keitakn-engineering-skills/.claude/skills/explain-visually/SKILL.md)
- 紹介記事: [AIに丸投げしないで理解するためのAI開発手法（2026年8月現在）](https://zenn.dev/avaintelligence/articles/dont-outsource-understanding-to-ai)
- 同梱: HTMLテンプレート、描画検証用Pythonスクリプト、上流のMITライセンス
- 利用時の前提: Google Chrome、Python 3、PRを扱う場合は認証済みの `gh`。図の描画にはMermaidのCDNを使用します。

ここでは外部スキルとして保管しています。エージェントのスキルディレクトリへの配置は別途行います。


## ディレクトリ構成

```text
external-skills/
├── README.md       # このカタログの説明と運用方針
├── sources.yaml    # upstream と取得条件の台帳
├── ATTRIBUTIONS.md # upstream の著作者・ライセンス・公開可否
└── vendor/         # ライセンス確認済みupstreamのスナップショット
    ├── cursor-pstack/
    └── keitakn-engineering-skills/
```

`vendor/` 配下の各ディレクトリは、どの upstream に対応するかが名前だけで分かるようにします。Cursor の `pstack` は単独スキルではなく、プラグイン設定・agents・skills を含むため、`skills/` だけを切り出さずプラグイン単位で保存します。ライセンスが確認できないソースは、出典だけを登録し、実体を公開しません。

## 利用上の注意

このリポジトリは upstream の代替・公式ミラーではありません。利用者は、各 upstream の最新情報とライセンスを確認してください。
