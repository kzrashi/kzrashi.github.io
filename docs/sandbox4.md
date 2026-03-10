# エンジニアのための Obsidian 知識管理ガイド

Yocto / React / TypeScript などの技術学習を例に、Obsidianで知識を効率よく蓄積・活用するための運用方法とVault構成をまとめる。

---

## 1. 基本方針

Obsidianの強みは **双方向リンク（`[[]]`）** によるノート間の関係構築にある。フォルダで「置き場所」を決めつつ、リンクとタグで「意味のつながり」を横断的に作るのがコツ。

運用の3原則：

1. **書く敷居を下げる** — Inboxにとりあえず放り込み、後で整理する
2. **1ノート1トピック** — 粒度を小さく保ち、リンクで組み合わせる
3. **定期的に振り返る** — MOC（Map of Content）で俯瞰し、リンク切れや孤立ノートを回収する

---

## 2. 推奨フォルダ構成

```
Vault/
├── 00-Inbox/              # 未整理メモの一時置き場
├── 10-Projects/           # 進行中プロジェクト（期限あり）
│   ├── yocto-custom-distro/
│   └── react-dashboard-app/
├── 20-Areas/              # 継続的に管理する領域（期限なし）
│   ├── Yocto/
│   ├── React/
│   ├── TypeScript/
│   ├── Linux-Kernel/
│   └── Career/
├── 30-Resources/          # リファレンス・参照情報
│   ├── Snippets/
│   ├── Cheatsheets/
│   └── Bookmarks/
├── 40-Archive/            # 完了・非アクティブなノート
├── 90-Templates/          # テンプレート置き場
└── 99-Meta/               # MOC・ダッシュボード・運用ルール
    ├── MOC-Yocto.md
    ├── MOC-React.md
    ├── MOC-TypeScript.md
    └── Dashboard.md
```

### なぜこの構成か

| 層 | 役割 | 例 |
|---|---|---|
| `00-Inbox` | 「考える前に書く」を可能にする安全地帯 | 調べ物中のメモ、思いつき |
| `10-Projects` | 今やっていることをまとめる。終わったら Archive へ | Yoctoカスタムディストロ構築 |
| `20-Areas` | 技術ドメインごとの永続的な知識ベース | Yocto, React, TS の学習ノート |
| `30-Resources` | 繰り返し参照するスニペットやチートシート | bitbakeコマンド一覧、TSの型ユーティリティ集 |
| `99-Meta` | 全体を俯瞰するMOCやダッシュボード | 各技術のMOCページ |

> この構成は Tiago Forte の **PARA メソッド**（Projects / Areas / Resources / Archives）をベースにしている。番号プレフィックスでサイドバーの並び順を固定できる。

---

## 3. タグ設計

タグはフォルダを横断する「属性」として使う。フォルダ＝置き場所、タグ＝性質という棲み分けが重要。

### 推奨タグ体系

```
# ノートの種類（type）
#type/concept       … 概念・原理の説明
#type/howto         … 手順・やり方
#type/troubleshoot  … トラブルシュートの記録
#type/til           … Today I Learned（小さな発見）
#type/decision      … 設計判断・意思決定の記録
#type/snippet       … コードスニペット
#type/question      … 未解決の疑問

# 学習ステータス
#status/seed        … 書きかけ・調査中
#status/growing     … ある程度まとまった
#status/evergreen   … 十分に成熟したノート

# 技術ドメイン（Areas と対応）
#domain/yocto
#domain/react
#domain/typescript
#domain/linux
```

### タグ運用のコツ

- タグは **2階層まで** に抑える（`#type/howto` は OK、`#type/howto/advanced` は避ける）
- ドメインタグはフォルダと重複するが、**Dataviewクエリやグラフビューで横断検索** するために付けておく価値がある
- `#status/*` を活用して「育てるべきノート」を定期的に洗い出す

---

## 4. テンプレート

`90-Templates/` に以下のテンプレートを用意しておく。Templaterプラグインを使うとさらに自動化できる。

### 4.1 学習ノート（概念）

```markdown
---
aliases: []
tags:
  - type/concept
  - status/seed
  - domain/
created: {{date:YYYY-MM-DD}}
---

# {{title}}

## 一言で言うと

（この概念を1〜2文で説明）

## 詳細

（背景、仕組み、なぜ重要か）

## コード例 / 具体例

```
（必要に応じて）
```

## 関連ノート

- [[]]

## 参考

- [リンク](URL)
```

### 4.2 トラブルシュート

```markdown
---
tags:
  - type/troubleshoot
  - status/seed
  - domain/
created: {{date:YYYY-MM-DD}}
---

# {{title}}

## 症状

（何が起きたか）

## 環境

- OS:
- バージョン:

## 原因

（調査して分かったこと）

## 解決策

```
（コマンドやコード）
```

## 教訓

（次回同じ状況になったときのために）

## 関連ノート

- [[]]
```

### 4.3 設計判断（ADR風）

```markdown
---
tags:
  - type/decision
  - status/growing
  - domain/
created: {{date:YYYY-MM-DD}}
---

# {{title}}

## コンテキスト

（なぜこの判断が必要になったか）

## 選択肢

| 案 | メリット | デメリット |
|---|---|---|
| A |  |  |
| B |  |  |

## 決定

（何を選び、なぜそうしたか）

## 結果・影響

（決定後に分かったこと。後から追記してよい）
```

---

## 5. MOC（Map of Content）の作り方

MOCは特定ドメインの「目次ページ」。ノートが増えてきたら作成する（目安: 10ノート以上）。

### 例: `MOC-Yocto.md`

```markdown
---
tags:
  - type/moc
  - domain/yocto
---

# Yocto MOC

## 基礎概念
- [[Yoctoとは]]
- [[OpenEmbeddedとの関係]]
- [[Bitbakeの仕組み]]
- [[レイヤー構造]]

## レシピ開発
- [[bbファイルの書き方]]
- [[do_fetchからdo_packageまでのタスクフロー]]
- [[DEPENDS と RDEPENDS の違い]]
- [[独自パッケージの追加手順]]

## カスタマイズ
- [[カスタムディストロの作り方]]
- [[カスタムイメージの定義]]
- [[local.confの主要変数]]

## デバッグ・トラブルシュート
- [[bitbake -e で変数を確認する]]
- [[devshellの使い方]]
- [[パッチが当たらないときの対処]]

## 未整理・調査中
- [[Yocto 5.x の変更点]] #status/seed
```

### 例: `MOC-React.md`

```markdown
---
tags:
  - type/moc
  - domain/react
---

# React MOC

## コア概念
- [[JSXとは]]
- [[コンポーネントのライフサイクル]]
- [[useState / useEffect の使い分け]]
- [[Reactの再レンダリング条件]]

## パターン・設計
- [[Container-Presentationalパターン]]
- [[カスタムフックの設計指針]]
- [[状態管理の選択肢比較]]

## エコシステム
- [[React Router v6 の基本]]
- [[Vite + React のセットアップ]]
- [[React Testing Library の書き方]]

## TypeScript連携
- [[ReactコンポーネントのProps型定義]]
- [[ジェネリクスを使ったカスタムフック]]
→ 詳細は [[MOC-TypeScript]] も参照
```

MOCのポイント：

- **手動でキュレーション** する。自動生成だけに頼らない
- セクション分けは「学習者がたどる順序」を意識する
- `#status/seed` のノートも載せておくと「次に調べること」が見える

---

## 6. 推奨プラグイン

| プラグイン | 用途 | 優先度 |
|---|---|---|
| **Templater** | テンプレートの自動展開・日付挿入 | ★★★ |
| **Dataview** | タグやメタデータでノートを動的に一覧表示 | ★★★ |
| **Quick Switcher++** | ノート検索の高速化 | ★★★ |
| **Calendar** | Daily Note との連携 | ★★☆ |
| **Git** | Vault全体をGitで自動バックアップ | ★★☆ |
| **Excalidraw** | アーキテクチャ図や概念図を描く | ★★☆ |
| **Kanban** | プロジェクトのタスク管理 | ★☆☆ |

### Dataview の活用例

`99-Meta/Dashboard.md` に埋め込む：

````markdown
## 育てるべきノート（seed → growing へ）

```dataview
TABLE created, file.folder AS "場所"
FROM #status/seed
SORT created DESC
LIMIT 20
```

## 最近の TIL

```dataview
LIST
FROM #type/til
SORT created DESC
LIMIT 10
```

## Yocto の未解決疑問

```dataview
LIST
FROM #type/question AND #domain/yocto
```
````

---

## 7. 日常の運用フロー

### 日次（5〜10分）

1. 学んだことを `00-Inbox` にメモする（テンプレートを使って素早く）
2. 余裕があれば1〜2個のInboxノートを適切なフォルダへ移動し、リンクを張る

### 週次（15〜30分）

1. `00-Inbox` を空にする（整理 or 削除）
2. `#status/seed` のノートを1つ選んで肉付けし `#status/growing` へ
3. グラフビューを眺めて孤立ノートにリンクを張る
4. Dashboard の Dataview を確認する

### 月次（30分〜1時間）

1. MOCを見直してノートの追加・並べ替え
2. 完了したプロジェクトを `40-Archive` へ移動
3. タグの乱立がないかチェック（類似タグの統合）

---

## 8. 実践 Tips

### ノートの命名規則

- 日本語OK。検索しやすい名前を優先する
- 「〇〇とは」「〇〇の使い方」のように意味が分かるタイトルにする
- ファイル名にプレフィックス番号は不要（フォルダとリンクで管理する）

### リンクの張り方

- 書いている途中で関連トピックが浮かんだら、**存在しなくてもリンクを張る**（`[[まだないノート]]`）。後から中身を書けばよい
- これが Obsidian 最大の武器。「先にリンクを張り、後でノートを埋める」ことで知識のスケルトンが先にできる

### Yocto / React / TypeScript 横断の例

TypeScriptの型システムの知識はReactのProps型定義にも使う。こうした横断的な関係はフォルダでは表現できないが、リンクなら簡単：

```markdown
<!-- 20-Areas/TypeScript/ジェネリクスの基本.md の中で -->
## React での活用
- [[ReactコンポーネントのProps型定義]] でジェネリクスを使うパターン
- [[カスタムフックの型付け]]
```

同様に、Yocto上でReactアプリをビルドするプロジェクトがあれば：

```markdown
<!-- 10-Projects/yocto-react-kiosk/ の中で -->
- Yocto側: [[カスタムイメージの定義]]
- React側: [[Vite + React のセットアップ]]
- ビルド統合: [[YoctoレシピからReactアプリをパッケージする方法]]
```

### Gitでのバックアップ

- Obsidian Git プラグインで自動コミット（10分間隔など）
- `.obsidian/workspace.json` は `.gitignore` に入れる（環境依存のため）
- プライベートリポジトリを使うこと

---

## 9. まとめ

| やること | 効果 |
|---|---|
| PARA構成でフォルダを作る | ノートの置き場所に迷わない |
| テンプレートで型を決める | 記録の敷居が下がり粒度が揃う |
| タグで性質を横断的に付ける | Dataviewで動的な一覧が作れる |
| MOCで領域ごとに俯瞰する | 知識の全体像と抜け漏れが見える |
| リンクを先に張る | 知識のスケルトンが自然に育つ |
| 週次で振り返る | Inboxが溜まらず、ノートが成熟する |

完璧なノートを目指す必要はない。**「書く → リンクする → 育てる」** のサイクルを回し続けることが最も重要。
