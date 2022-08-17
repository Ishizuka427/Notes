# 賢く「振り分ける」ための Topology Aware Hints - [@y_taka_23](https://twitter.com/y_taka_23)
## Topology Aware Hints
### Topology とは
- Node をグループ化したもの
- Rack, Zone, Region などの障害範囲(死ぬときに一度に死ぬ範囲)として使われることが多い

Pod が単一の Zone に固まっていると Zone の障害で全滅の可能性があるため散らしたい  
-> Availability Zone はコスト高

## ボツKEP集
### Service Topology
- Service に topologyKeys を明示  
- 複数の Key を指定すると、通信先が見つかるまで順番に探しに行く  
-> わざわざ指定するので認知負荷高　※v1.20 で Deprecated

### EndpointSlice Subsetting
- 単一の大きな Endpoints リソースを、自動で複数の小さな EndpointSlice に分割する  
- Service Topology のような Topology 指定が不要になる  
-> 分割によって　EndpointSlice　数、更新が増加する ※KEPのみでお蔵入り

## 本題
### Topology Aware Hints
- Service　にアノテーションを追加
`service.kubernetes.io/topology-aware-hints: auto`
- EndpointSlice は分割されない  
-> オーバーヘッドがかかるため
EndpointSlice Controller が hints.forZones フィールドを自動で設定

### 何ができる？
Zone 内の Node の総 CPU 数に比例して、ルーティングする Pod を按分する  
-> すげー！

小数点込みで割り算した個数が、実際の Pod 数から乖離しはじめた(具体的には120％↑)場合、Hint は無効になる  
-> 常に Zone 内で通信を行おうとはせず、状況に応じて偏りすぎる場合は適宜フェイルオーバーする
