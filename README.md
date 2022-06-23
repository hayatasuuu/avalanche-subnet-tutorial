# avalanche-subnet-tutorial

## 必要要件

```
% uname -mrs
Darwin 21.5.0 arm64

% docker -v
Docker version 20.10.8, build 3967b7d
```

## インストール

### Dockerコンテナの作成

```
docker image pull ubuntu:18.04
docker container run -it -d --name ubuntu ubuntu:18.04
```

### Ubuntuのセットアップ

```
docker container exec -it ubuntu /bin/bash
apt-get update
apt-get install curl -y
```

### avalanche-cliのインストール

```
curl -sSfL https://raw.githubusercontent.com/ava-labs/avalanche-cli/main/scripts/install.sh | sh -s
cd bin
export PATH=$PWD:$PATH
```

## クイックスタート

`avalanche subnet create <subnetName>`で一発。

```
avalanche subnet create mysubnet
```

作成したSubnetを確認するには以下。

```
avalanche subnet list
+----------+----------+----------+-----------+----------+
|  SUBNET  |  CHAIN   | CHAIN ID |   TYPE    | DEPLOYED |
+----------+----------+----------+-----------+----------+
| mysubnet | mysubnet |       26 | SubnetEVM | No       |
+----------+----------+----------+-----------+----------+

avalanche subnet describe mysubnet
 _____       _        _ _
|  __ \     | |      (_) |
| |  | | ___| |_ __ _ _| |___
| |  | |/ _ \ __/ _  | | / __|
| |__| |  __/ || (_| | | \__ \
|_____/ \___|\__\__,_|_|_|___/
+-------------+----------+
|  PARAMETER  |  VALUE   |
+-------------+----------+
| Subnet Name | mysubnet |
+-------------+----------+
| ChainId     |       26 |
+-------------+----------+
| Token Name  | HYT      |
+-------------+----------+

```

HYT（HAYATO）コインができました＾＾