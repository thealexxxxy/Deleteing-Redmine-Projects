## Tool for deleteing Redmine Projects which have not been updated for a period of time.

Redmineでプロジェクトが増えてくると
ファイルが増えてサーバのDisk容量が足りなくなってくる。

そこで、一定期間なにも更新されていないプロジェクトを抽出し、
特定のプロジェクトとそのプロジェクトに紐ずいている添付ファイルを削除する。


### Requirements
・ Ruby >= 2.0 or 1.8

### Usage
ファイルの編集
##### 1.DBの関連など環境に合わせて編集する
DBに接続
```
ActiveRecord::Base.establish_connection(
            :adapter  => 'mysql2',
            :host     => 'localhost',
            :username => 'hogehoge',
            :password => 'hogehoge',
            :database => 'hogehoge'
)
```

##### 2.更新期限の設定
```
from = Time.now
to   = from - 2.year
```

上記の設定では2年以上更新されていないプロジェクトを抽出する

```
to   = from - 6.month
```
また、6ヶ月間など月単位で指定したい時は上記のように設定

##### 3.redmine添付ファイルのディレクトリの指定
```
if cmd == "go"

  attachment_disk_filename.each do |attachment_disk_filename|
    delete_files = "/home/www/redmine/files/" + attachment_disk_filename   
```
### Runing script

##### 更新されていないProjectの抽出
```
ruby script.rb
```

出力されたProjectのうち除外したいものがあれば以下の様に
Project名を追記して除外する。

```
     ######## //に除外sitaProject名を書く
     # ex.)
     # /hogehogeプロジェクト/
     #
  
     if /hogehogeプロジェクト/ !~ not_update_project2.name
```

##### 更新されていないProjectの削除
```
ruby script.rb go
```
  




