# nikotaronosuke

## AIと一緒に、プロダクトを作る

Web / Mobileの個人プロダクトを企画・設計・開発しています。

生成AIを実装や調査のパートナーとして使いながら、  
**何を作るか、なぜその仕様にするか、どこまでAIに任せるか、実際に使える状態になったか**を自分で判断してプロダクトを形にしています。

コードが動くことだけではなく、実際の画面や実機で確かめ、違和感があれば仕様から変えることを重視しています。

---

## Projects

### Caplog / カプログ

**デートプランの共有から始まり、「実際にその場所へ行った人の体験」を残す方向へ発展したWeb / Mobileサービス。**

`Next.js` `TypeScript` `Supabase` `Cloudflare Workers` `Expo` `React Native` `Google Maps / Places`

Web版、Mobile版、認証、DB / Storage、地図、投稿、写真、コメント、いいね、保存、共有などを開発。  
Mobileから外部APIを直接呼ばず、専用Cloudflare WorkerをAPI Gatewayとして分離し、認証・rate limit・secret・外部APIコストをサーバー側で管理する構成にしました。

開発途中では「デートプランそのものより、スポット単位の実体験の方が価値を出せるのでは」と考え直し、既存データを検証してから `spot_log` を追加。文字中心だったフィードも実際の画面を見て捨て、写真中心の発見型UIへ変更しました。

**Status:** Web production / Mobile development  
**Case Study:** [Caplog — Product & AI Development](case-studies/caplog.md)

---

### Dog App / 犬アプリ

**スマホの中の“うちの子”と一緒に過ごしながら、近くの犬たちの気配も感じられるモバイルプロトタイプ。**

`Flutter` `Dart` `Flame` `Supabase` `Google Sign-In` `LINE Login`

Flutter + Flameで、複数の犬が2Dの広場を自律的に歩き回る体験を実装しました。

当初は、

**犬の写真 → AIでその犬そっくりの四方向ドット絵を自動生成**

する構想でした。

実際に生成・実機検証すると、向きや模様の一貫性を全ユーザーで安定させることが難しいと判明。技術を追い続けるのではなく、

**完全自動生成 → 犬種テンプレート + 選択式カスタマイズ**

へプロダクト側の設計を変更しました。

LINEログインも最初のOAuth案に固執せず、最終的にLINE native login + Supabase Edge Functionの構成へ変更し、Pixel実機で認証後にアプリ本体まで到達するところまで確認しています。

**Status:** Prototype / Frozen  
**Case Study:** [Dog App — Product & AI Development](case-studies/dog-app.md)

---

### Uradori / ウラドリ

**「行こうと思っていた店がダメだった。じゃあ今からどこへ行く？」を解くための現地代替提案プロダクト。**

`React Native` `Expo` `TypeScript` `Cloudflare Workers` `Google Places` `Google Routes / Route Matrix`

普通の店舗検索ではなく、現在地や任意地点、徒歩 / 車、移動時間、ジャンル、予算、静かさ、一人向きなどを組み合わせ、**今この状況で次に行ける店**を10件前後から選べる体験を目指しました。

ジャンル分類もAPIの都合ではなく「今何を食べたいか」を優先。Google Placesで専用typeが弱い日本固有ジャンルにはText Searchを組み合わせ、候補不足時には検索範囲を段階的に緩和し、その変更をユーザーへ明示する設計にしました。

検索・店舗情報・Route Matrix・条件評価などを実装しましたが、開発が進むほど、

- 利用に比例して増える外部APIコスト
- 「静か」「一人向き」「臨時休業」など深い店舗情報を高精度で維持する難しさ
- Google Maps以上の独自価値を継続して作る難しさ

が大きくなりました。

**作れるかではなく、利用者が増えた後も成立するか**を考え、現在は停止しています。

**Status:** Paused  
**Case Study:** [Uradori — Product & AI Development](case-studies/uradori.md)

---

### Private Project

現在、新しいWeb / Mobileプロダクトを開発しています。

過去の開発でWeb、Mobile、設計資料、AIとの共有情報が分散した経験から、今回は最初から

`Web / Mobile / Worker / Shared / Database`

を1つのmonorepoへ統合。

さらにChatGPTとClaude Codeの共有情報を、

`CURRENT` / `DECISIONS` / `TODO` / `sessions`

に分離し、GitHubをAI間の共有正本として使っています。

詳細は現在非公開です。

---

## How I build

### Human decides, AI implements

開発では、おおむね次のように役割を分けています。

**nikotaronosuke**  
Product concept / Specification / UX decisions / Final approval / Real-device verification

**ChatGPT**  
Planning / Discussion / Review / Implementation task design

**Claude / Claude Code**  
Research / Implementation / Testing / Documentation

AIに全部を委ねるのではなく、影響が大きい変更ほど人間や別AIによるレビューを増やします。

### Test the product, not just the code

AIやテストが「成功」と言っても、それだけでは完了にしません。

実際の画面や実機で確認し、

- UIが使いづらければレイアウトを変える
- 開発途中の都合がユーザーへ露出していれば仕様を変える
- 外部APIの前提が崩れればfallbackを作る
- 技術的に成立しなければ、技術ではなくプロダクト側を変える

という進め方をしています。

### Protect production from AI mistakes

AIを積極的に使うからこそ、危険な操作にはガードを入れています。

- secret / tokenを不用意に扱わない
- DB write / migrationを勝手に実行させない
- deployを勝手に実行させない
- force pushなどの危険なGit操作を禁止する
- 想定外の変更があれば停止する
- 高リスク変更は別のレビュー工程へ戻す

AIの能力を上げるだけでなく、**AIが間違えた時の被害範囲を小さくすること**も開発の一部だと考えています。

---

## Current focus

今は新しい機能を作ることだけではなく、

**AIと一緒に作ったものを、どう検証し、どう記録し、どう次の開発へ引き継ぐか**

まで含めて、開発方法そのものを改善しています。
