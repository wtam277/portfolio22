# 環境構築方法(Dockerを使用)

## コンテナイメージのビルド
```
$ docker build . -t middle_examination_sql
```

## コンテナ作成&起動(初回だけ)
ビルドしたコンテナイメージからコンテナを起動
3306ポートを疏通
```
$ docker run -d --name middle_examination_sql -p 3306:3306 middle_examination_sql
```

## コンテナ内に入る
コンテナ内のシェルを起動
```
$ docker exec -it middle_examination_sql bash

```

## コンテナからローカルに戻る
コンテナ内で実行(`control + d`でもOK)
```
# exit
```

## 初期データの作成
コンテナ内で初期データ作成sql実行
```
# mysql -pcollege < employees.sql
```

## データベースにログイン
```
# mysql -pcollege
```


## データベースからログアウト
```
mysql> exit
```

## コンテナの停止
※ ローカルで実行
```
$ docker stop middle_examination_sql
```

## コンテナの削除
コンテナが停止した状態で
```
$ docker rm middle_examination_sql
```

# 提出方法
- 回答をanswersディレクトリのそれぞれのファイルに記載してください。
- 回答の作成が終了したらプルリクエストを作成し、カリキュラムからレビュー依頼を行ってください。
