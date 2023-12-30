https://developer.confluent.io/tutorials/kafka-console-consumer-primitive-keys-values/kafka.html

consumerで明示的ににデシリアライザーを指定する方法を学んだ。
デシリアライザーを定義しないと文字化けをする。なぜかって言うと デシリアライザーを定義しないとデータがストリング型だと認識されるため明示する必要がある。
