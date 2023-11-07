# Datadog 新機能アップデート

## DASH で発表された新機能振り返り

### LLM AI エコシステム
(まだ未公開)
- Bits AI  
Ask Bits AI
  - 「何ができますか」
  - 「tax-return-web の状況を教えて」

### 次世代のオブザーバビリティ

- Frex Tier  
  従来の Standard Tirer と比較して中長期的 ◎
- Enable APM Instrumentation
- トレースクエリ  
  Search for traces トレースの検索で 2 件以上検索できるようになった

- AI による Error の修正案  
  Error Tracking 　で検出した Error について、コードの修正案をだしてくれる

### DevOps におけるセキュリティ

- Security inbox  
  CSM

- アプリコード内のリアルタイム脆弱性検知  
  静的解析  
  static Analysis

- Quality Gates  
  モバイルでユーザーの実際の動作を録画できるようになった（Web ではできたらしい）

### Shift Left 開発エクスペリエンス

### Cloud コスト最適化

- Cloud cost レコメンデーション  
  AI で最適なコスト削減のアドバイスを行う

## 最新機能アップデート

- 直近でデプロイを実施したタイミングをダッシュボードにオーバーレイできるようになった
- セッションリプレイからブラウザテストを自動生成  
  もともとセッションリプレイの機能はあった → セッションリプレイから、ボタンポチでテストを自動生成できるようになった

- Current blueprint  
  Cloudcraft×Datadog

- ASM Vulnerability Management  
  本番環境の OSS の脆弱性を検知

- CIS ベンチマークのサポート  
  k8s, Docker などにはあった機能  
  Linux ディストリビューションにも搭載  

## APM 　セットアップの新たな選択肢

- APM Remote cooonfigration  
  k8s のみの機能  
  webUI から APM の設定が簡単にできる  
  従来はまず導入時にアプリケーションサイドに連携をお願いする必要があったが、今回の機能でまず APM の恩恵をすぐに見ることができる  

# 今さら聞けない、Datadog を活用した複雑に絡み合ったシステムのパフォーマンス改善

- trace  
  ボタン発火でどのようなサービスが使われているかがわかる  
  → Service Catalog を実現している  
  写真あり  
  tax-return が Service Catalog に表示されないのは trace の設定ができていないから？  

- エラーの起こったユーザーセッションを RUM  
  RUM について知りたい  

- APM Error 時に Span の特定までできたら、Code Hotspots

# ライトニングトーク 1 株式会社キュービック 森 祐太朗さん

Datadog のコストも監視しよう  
推定使用量メトリクス  
cost のメトリクス監視ができる  

# ライトニングトーク 2 株式会社ナレッジワーク Naoto Higuchi さん

エラーログ監視改善のために  

既存の ErrorLog の監視方法と課題  
GCP→Datadog→Slack  
ErrorTracking  
類似の Error を自動的に分類してくれる  
Count 分類された Error 数が一定超えたら通知  
New issue 新しい Error が  
まだ β 版  
分類精度にはまだ疑念有り  

# ライトニングトーク 3 Cloudbase 株式会社 ryuke さん

ErrorTrackingLogs  
大量のバッチジョブの Error 監視  
すぐに対応の必要はないが原因調査をしたい ErrorLog の可視化
  
