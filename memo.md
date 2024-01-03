https://developer.confluent.io/tutorials/how-to-count-messages-on-a-kafka-topic/kafka.html

トピックのメッセージの数をカウントするには、kcatというツールを使用してメッセージを読みとる
オフセットだと重複があったり、ただしくメッセージをカウントすることができない
ただし、実際にメッセージを読み取ってカウントしている以上時間はメッセージの数に線形に比例する

https://developer.confluent.io/tutorials/change-topic-partitions-replicas/ksql.html?session_ref=https://developer.confluent.io/tutorials/kafka-console-consumer-read-specific-offsets-partitions/kafka.html#write-the-program-interactively-using-the-cli

ksqlを使用したパーティション・レプリケーションを変更する方法
1. トピック1をあるksqlのテーブルに流す(s1)
1. 別のテーブルs2を作成し、s1の内容をそのままもってくる(トピック2とする)。この時にパーティションやレプリケーションを変更する


https://www.confluent.io/blog/put-several-event-types-kafka-topic/?_ga=2.226889565.1306882562.1703759849-607933860.1703295923&_gac=1.195340766.1703467070.CjwKCAiAyp-sBhBSEiwAWWzTnsNUP9KSwTothaiJ3GJBLTqUan2WUl43knoBrHPIgE3XWHceVSayixoCjlgQAvD_BwE&_gl=1*xzqmyh*_ga*NjA3OTMzODYwLjE3MDMyOTU5MjM.*_ga_D2D3EGKSGD*MTcwNDExNDQzOC4zMS4xLjE3MDQxMTUyMjguNTYuMC4w

同一のトピックにまとめるべきイベント
- 順序を考慮すべきイベントは同一のトピックにまとめる
  - タイムスタンプで順序を決める方法はハンドリングが難しい（不可能？）
- 同一のトピックに、順序関係はあるがデータ形式が異なるイベントを集めることができる
  - スキーマの設定を、トピックごと・トピックのレコードごと・レコードごと、など柔軟に決めることができる。異なるイベントを一つのトピックで扱いたい場合は、
  「トピックのレコードごと」のスキーマを設定して別のイベントとして扱えば良い

https://developer.confluent.io/tutorials/split-a-stream-of-events-into-substreams/kstreams.html
インプットトピックから条件分岐で別のトピックにデータを流し込むことができる。
split()とbranch()を使用する。

https://developer.confluent.io/tutorials/merge-many-streams-into-one-stream/kstreams.html
複数のトピックのデータを一つのトピックにマージすることができる

https://developer.confluent.io/tutorials/filter-a-stream-of-events/kstreams.html
filterメソッドを使用すると、イベントから不要なものをフィルタリングして他のトピックに渡すことができる
コンシューマーでイベントをフィルタリングするのではなくフィルタリングして別のトピックに渡している。

https://developer.confluent.io/tutorials/create-stateful-aggregation-count/confluent.html?session_ref=https://developer.confluent.io/tutorials/create-stateful-aggregation-count/confluent.html?session_ref=https://developer.confluent.io/tutorials/kafka-console-consumer-read-specific-offsets-partitions/kafka.html
グループでまとめてカウントする方法について
グループ化したものを別のトピックに渡す。新しいイベントが来るごとに集計用のトピックが更新されて新しい結果が表示される（UPSERT）
