# constructivism

日本語ドキュメントの構成（章立て・セクション順序）を選ぶ、Microsoft APM（Agent Package Manager）形式のスキルです。

ハーネスから渡される「目的・読者・伝えたいメッセージ・内容・制約」をもとに、技術文書（チュートリアル、手順書、リファレンス、解説、技術記事、設計書、ADR など）、学術・教育（論文、教材）、ビジネス文書（報告書、企画書、稟議書、議事録、障害報告、通知、メールなど）のカタログから最適な構成を選び、日本語見出しの骨子と選択理由を出力します。ファクト収集や論理検証は行いません。

## インストール

```bash
apm install asuka1975/constructivism
```

配置先は Claude Code が `.claude/skills/constructivism/`、GitHub Copilot・Cursor・Codex・Gemini などが `.agents/skills/constructivism/` です。配置先のプレビューは `apm install --dry-run --target claude` で確認できます。

## 構成

```
.
├── apm.yml
├── docs/
│   └── jp-doc-structure-research.md   # 調査レポート（本スキルの根拠。内容はこれを正とする）
└── .apm/skills/constructivism/
    ├── SKILL.md                        # 判断手順と出力形式
    ├── references/
    │   ├── decision-rules.md           # 判断軸・決定木・選択マトリクス
    │   ├── catalog-technical.md        # 技術ドキュメント系の骨子カタログ
    │   ├── catalog-academic-edu.md     # 学術・教育系の骨子カタログ
    │   ├── catalog-business.md         # ビジネス文書系の骨子カタログと判別表
    │   ├── japanese-conventions.md     # 日本語文書の慣習（結論の位置、文体、標題と見出し）
    │   └── hybrid-and-checklist.md     # ハイブリッド、逸脱の条件、品質チェックリスト
    └── examples/
        └── sample-outputs.md           # 入力→出力の例（稟議書、チュートリアル、技術記事）
```

## 使い方

スキルは次の入力を受け取り、「構成選択結果」「骨子」「構成チェック」の3部からなる Markdown を出力します。

- 目的：読者が読後に何をするか（決める／報告を受ける／作業する／学ぶ／調べる／理解する／動かされる／検証する）
- 読者：役割、専門性、読む姿勢
- メッセージ：中心となる主張・結論と、その種別
- 内容：手順的／概念的／参照的／時系列／データ中心と、主要な要素の一覧
- 制約：指定書式、媒体、分量上限、社内か社外か

判断の既定は「組織の定型があれば最優先」「読者の目的で系統を決める」「結論は冒頭に置く」「専門性で前置きと深さを調整する」です。具体的な入力と出力の例は `examples/sample-outputs.md` を参照してください。

## 検証

```bash
apm audit --file .apm/skills/constructivism/SKILL.md
```

## ライセンス

MIT
