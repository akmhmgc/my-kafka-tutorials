https://developer.confluent.io/tutorials/error-handling/kstreams.html

Kafka内で捕捉することができないエラーが発生した時は
アプリケーションをシャットダウンする/別のスレッドに変更する
などのエラー対処方法を設定することができる

ただし、一定の時間以内に一定以上のエラーが発生した場合はアプリケーションを遮断する、といった処理を入れる必要がある。
なぜならば、一定数以上のエラーは偶発的なものではなく根本的に解決すべき（アプリケーションを落とすべき）エラーであるからである。

