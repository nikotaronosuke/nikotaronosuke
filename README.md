# nikotaronosuke

## AIと一緒に、プロダクトを作る

Web / Mobileの個人プロダクトを企画・設計・開発しています。

ChatGPT / Claude / Claude Codeなどの生成AIを実装・調査・レビューのパートナーとして使いながら、企画、仕様、UX、最終判断、実機確認を行っています。

AIにコードを書かせること自体ではなく、**何を作るかを決め、実際に使い、必要なら仕様から変えること**を重視しています。

---

## 稼働中のプロダクト

### Caplog / カプログ

デートやお出かけを「見つける・作る・記録する」ためのモバイル中心のプロダクト。

- [Public showcase](https://github.com/nikotaronosuke/caplog-showcase) — 実機スクリーンショット / 機能 / 技術設計
- [Web](https://caplog.jp) — 本番稼働中

`Expo` `React Native` `TypeScript` `Supabase` `Cloudflare Workers` `Next.js` `Google Maps / Places`

現在はMobileアプリを開発の中心にしつつ、Web版も継続運用しています。Showcaseでは地図、公開URL、App APIなどの設計判断も公開しています。

**状態:** Mobile 開発中 / Web 本番稼働中

---

### ぽいもの本舗

作ったもの・開発記録・技術記事・Web実験をまとめる、個人サイト / ポートフォリオ兼ブログ。

- [poimono.jp](https://poimono.jp)

`Astro` `TypeScript` `Cloudflare Workers Static Assets`

プロダクトだけでなく、調査・試作・ブラウザ上の実験作品まで含めて、自分の制作物を継続的に公開するホームベースとして運用しています。

**状態:** 本番稼働中 / 継続更新

---

### NINJA MAP / 忍者マップ

**「今、日本のどこに忍者がいる？」** をテーマに、現在体験できる忍者施設・体験を地図から探せる日英対応の旅行データベース。

- [ninjamap.jp](https://ninjamap.jp)
- [English](https://ninjamap.jp/en/)

`Astro` `TypeScript` `MapLibre GL JS` `Cloudflare Workers`

公式情報を優先した掲載確認と、公開用座標の検証フローを分けて運用しています。50スポットの初期データを整備し、日英ページ・地図・SEOを含めて公開しています。

**状態:** 本番稼働中 / データ継続更新

---

## 公開している道具

- [tiny-code-pet](https://github.com/nikotaronosuke/tiny-code-pet) — Claude Code / Codex の作業状況を画面隅の忍者で確認する Windows ネイティブのデスクトップ Pet（C#, MIT）
- [ai-problem-solving-memory](https://github.com/nikotaronosuke/ai-problem-solving-memory) — 複数の AI が同じ「問題」を証拠と状態ごと引き継ぐための MCP サーバー（TypeScript, MIT）
- [crowdworks-ai-survey-analyzer](https://github.com/nikotaronosuke/crowdworks-ai-survey-analyzer) — CrowdWorks のアンケート CSV をブラウザ内だけで集計・可視化（TypeScript）
- [jev-voice-decision](https://github.com/nikotaronosuke/jev-voice-decision) — 日本語音声をローカルSTTで文字起こしし、typed decisionをPythonの決定的な処理分岐につなぐWindowsデモ（Python, MIT）
- [excel-batch-tool](https://github.com/nikotaronosuke/excel-batch-tool) — Excel 本体なしで複数の Workbook を安全に一括解析・処理する Windows デスクトップアプリ（C# / WPF、開発中）
- [ja-stt-router-eval](https://github.com/nikotaronosuke/ja-stt-router-eval) — 日本語STTとLLMルーティングを再現可能な条件で評価するハーネス（Windows / Python）

---

<details>
<summary><strong>過去のプロトタイプ / 停止中プロジェクト</strong></summary>

### Dog App / 犬アプリ

スマホの中で“うちの子”と一緒に過ごす体験をテーマにしたモバイルプロトタイプ。

`Flutter` `Dart` `Flame` `Supabase`

2Dの広場で犬たちが自律的に過ごす体験や、認証・プロフィールなどを試作しました。実機で品質を確認しながら仕様を見直し、現在は凍結しています。

### Uradori / ウラドリ

「行こうと思っていた店がダメだった時、次にどこへ行くか」を素早く決めるための飲食店検索プロトタイプ。

`React Native` `Expo` `TypeScript` `Cloudflare Workers` `Google Places / Routes`

現在地や移動条件、ジャンルなどから代替候補を探す体験を開発しました。外部APIコストやサービスとしての成立性まで検討した上で停止しています。

</details>

---

## 進め方

- **企画・UX:** 自分で企画・仕様・UX・最終判断を行う
- **AI:** ChatGPT / Claude / Claude Codeを調査・実装・レビューに活用
- **検証:** コードだけでなく、実際の画面や実機で確認する
- **見直し:** 技術に無理に合わせず、必要なら仕様や方向性そのものを変える

---

## 今の関心

AIを使った個人プロダクト開発、UXプロトタイピング、実機検証、そして複数のAIと人間が無理なく協働できる開発フローに関心があります。
