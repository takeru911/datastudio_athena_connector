# DataStudio Athena Connector

Google DataStudioからAthenaに接続するためのConnectorです。

## 注意事項

IAMユーザーのaccess_keyとsecret_keyが必要になります。  
また現在のDataStudioのconnectorの仕様で2つのkeyを同時に設定できないので、deploy後に利用時の認証では`{accsee_key}_{secret_key}`と設定してください。  
内部で、`_`でsplitしてます。

IAMユーザーの権限は以下のものを必要としています。
 * athenaの実行権限
 * s3のathenaの実行結果を保存するbucketへの書き込み, 読み込み権限
 
## Deploy

 * https://developers.google.com/datastudio/connector/deploy
 
## Authentication

 * key認証です
   * 上記している通りに、access_keyとsecret_keyを`_`でつなげてください
 * 内部的に`ListNamedQueries` のAPIを実行し、結果が得られれば通すようにしています。
   * もっと良い方法あると嬉しい。
   
## Todo

 * Test
 * Refactoring
 * 頑張る
