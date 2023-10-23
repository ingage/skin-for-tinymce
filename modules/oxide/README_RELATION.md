# スキンの開発方法

## 準備

1. `git clone`でこのリポジトリを持って来る。
2. `yarn`で必要なパッケージをインストール。
3. `yarn oxide-start`でHMRなサーバが起動する。
4. `http://localhost:3000/`にアクセスして、デザインを確認しつつ調整する。

ポート番号がほかと被る場合は、`modules/oxide/gulpfile.js`のmonitorタスクの設定を直接変更するしかなさそう。注意。


## デプロイ

`yarn oxide-start`はビルドしたファイルをそのまま出力しているので、コミット・pushすればよい。

また`package.json`の`version`も更新すること。URLのハッシュが変わっているだけでは`yarn install`時に無視されるようなので必要。

一応`yarn oxide-build`で明示的にビルドすることも可能。

pushしてマージした後は、もちろん使用する側で見るバージョンを更新する。`yarn add`し直さないと駄目…。
