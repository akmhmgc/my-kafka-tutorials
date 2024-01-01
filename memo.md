https://developer.confluent.io/tutorials/how-to-count-messages-on-a-kafka-topic/kafka.html

トピックのメッセージの数をカウントするには、kcatというツールを使用してメッセージを読みとる
オフセットだと重複があったり、ただしくメッセージをカウントすることができない
ただし、実際にメッセージを読み取ってカウントしている以上時間はメッセージの数に線形に比例する

https://developer.confluent.io/tutorials/change-topic-partitions-replicas/ksql.html?session_ref=https://developer.confluent.io/tutorials/kafka-console-consumer-read-specific-offsets-partitions/kafka.html#write-the-program-interactively-using-the-cli

ksqlを使用したパーティション・レプリケーションを変更する方法
1. トピック1をあるksqlのテーブルに流す(s1)
1. 別のテーブルs2を作成し、s1の内容をそのままもってくる(トピック2とする)。この時にパーティションやレプリケーションを変更する
