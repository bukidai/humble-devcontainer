# humble-devcontainer

devcontainerでROS2 Humbleを簡単に始められるテンプレート

## 準備

.envファイルを作成するため、以下のコマンドを実行

`echo -e "USER_UID=$(id -u)\nUSER_GID=$(id -g)" > .env`

これで、実行ユーザと同じ権限でファイルを作ってくれます
