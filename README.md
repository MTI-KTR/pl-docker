# pl-docker

## PaintingLightをdockerで動かしたいときのメモ
先輩のを

###  とりあえずクローン
適当にディレクトリを作ってそこにクローンしてください。
```
git clone https://github.com/lllyasviel/PaintingLight.git
```
### docker hubからイメージを取得
```
sudo docker login
```
でログインして、

```
sudo docker pull mojako/paintinglight'
```
でイメージを持ってきてください。

ここから先は先輩のhttps://github.com/yaegasikk/gui-docker　とほぼ一緒です。

```
sudo docker run --gpus all  -v $(pwd):/user/local -d -p {$PORT}:22 mojako/paintinglight
 ```

で，コンテナの実行をしてください.{$PORT}は適当な空いてるポートを入れてください．

次に，別の端末からsshコマンドでサーバーにアクセスしてください．

 ```
ssh -X root@localhost -p {$PORT}
 ```

このとき，パスワードは**screencast**です．(必要であれば適宜Dockerfileをいじって変更してください．)

ログインすることができたら，

 ```
cd /user/local/PaintingLight/code

python3 example001.py
```

でしばらく立って画像が出てマウスを動かして遊んでみてください。
example001~045.pyまであります。




