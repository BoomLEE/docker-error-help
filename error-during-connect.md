## Error
error during connect: Get http://%2F%2F.%2Fpipe%2Fdocker_engine/v1.31/version: open //./pipe/docker_engine: The system cannot find the file specified. In the default daemon configuration on Windows, the docker client must be run elevated to connect. This error may also indicate that the docker daemon is not running.

## OS
windows7

## 確認
- Docker Hostが作られていないか
- Docker Hostが有効になっていないのか

## 確認・対応方法
1. __docker-machine ls__ コマンドで、ホストがあるか確認。
2. ホストがないなら作成する。例) __docker-machine create -d virtualbox default__
3. ホストがあるなら、__docker-machine active__ コマンドでそのホストがアクティブになっているか確認。
4. アクティブじゃないなら __eval $(docker-machine env ホスト名)__ コマンドでアクティブにする。
5. アクティブになっていてもだめなら __docker-machine restart ホスト名__ でホストを再起動する。
