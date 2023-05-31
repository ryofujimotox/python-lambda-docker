# How to Use

## 1. Docker起動

``` bash
docker build -t hello-world .
docker run -p 9001:8080 hello-world
```

### port9000はエラーでた

マニュアル通りのポートでやるとエラーがでた。すでに使っていた？・・
https://docs.aws.amazon.com/ja_jp/lambda/latest/dg/images-create.html#images-create-from-base

``` bash
docker run -p 9000:8080 hello-world
docker run -p 9000:8000 hello-world
```

エラー内容

``` bash
curl: (56) Recv failure: Connection reset by peer
```

## 2. 動作確認

``` bash
curl -XPOST "http://localhost:9000/2015-03-31/functions/function/invocations" -d '{}'
```
