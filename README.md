list-gae-resources
==================

A list of GAE learning resources

言語
--

Java とか Go で書ける

FW
--

Java の場合: Slim3

Go の場合: Martini

まあ、DataStore は ORM もついてるし別に気にすることはない。

主要な機能（各言語に binding がある）
---

- イイ感じにスケールする VM
- DataStore (BigTable)
- Google Cloud Storage との連携
- Google Cloud SQL との連携
- Log
- 管理機能
- Memcache
- TaskQueue

制限事項
---

- 外部へのリクエストを叩けない。リクエストを叩くための専用の機能コールが必要。
  * ゆえに、外部 API の利用は絶望的（Pusher とかですら。）
- 色んなプロセスを立てたり出来ない
  * ゆえに、fluentd とか mackerel とかは不可能（まあ要らないけど。）
- websocket 等, HTTP or HTTPS 以外のことが出来ない. また、HTTP のタイムアウトは 30 秒.
  * Channel という機能が用意されているが、当然のごとくロックインされる。あと iOS, Android 向けのクライアントライブラリも存在しない。

これだけの制限事項があって、良さって何？

1. デプロイがカンタン（heroku 並）
2. 管理要らない（勝手にスケールする）
3. DataStore は無駄にスケールする

DataStore について
---

Google Cloud DataStore というのがあるが、実体は AppEngine の DataStore にアクセスする API.

リソース
---

- http://tatsu-zine.com/books/gaeforjava 多分一番最新の本（2012年）
