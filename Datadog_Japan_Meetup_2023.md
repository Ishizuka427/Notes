# Datadog 新機能アップデート

## DASH で発表された新機能振り返り

### Bits AI  
https://www.datadoghq.com/ja/blog/datadog-bits-generative-ai/  
![image](https://github.com/Ishizuka427/Notes/assets/56011102/92bca02f-0f7e-404e-9f06-8ad8eb2f7a2a)

`Ask Bits AI`  
問いかけの例:  
  - 「何ができますか」
  - 「tax-return-web の状況を教えて」

### Frex Tier  
https://www.datadoghq.com/ja/blog/flex-logging/
  ログの保持期間。従来の Standard Tirer と比較して中長期的に ◎
### Enable APM Instrumentation
https://docs.datadoghq.com/ja/tracing/trace_collection/single-step-apm/?tab=linux%E3%83%9B%E3%82%B9%E3%83%88%E3%81%BE%E3%81%9F%E3%81%AFvm
### トレースクエリ  
  Search for traces トレースの検索で 2 件以上検索できるようになった

### AI による Error の修正案  
  Error Tracking 　で検出した Error について、コードの修正案をだしてくれる

### Security inbox  
  CSM

### アプリコード内のリアルタイム脆弱性検知  
  静的解析  
  static Analysis

### Quality Gates  
  モバイルでユーザーの実際の動作を録画できるようになった（Web ではできたらしい）


---
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
  
