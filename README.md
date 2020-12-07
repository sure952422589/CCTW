## CCTW

## 目录
* [基本原型](./docs/basic_type.md)
* [工作量证明](./docs/pow.md)
* [持久化和命令行接口](./docs/persistence-and-cli.md)
* [交易（1）](./docs/transaction.md)
* [地址](./docs/address.md)
* [交易（2）](./docs/transactions-2.md)
* [网络](./docs/network.md)

## 依赖
1. 安装python依赖
`pip install -r requestments.txt`
2. 安装couchdb(每个节点都要安装)
	1. 直接安装，参考https://www.yiibai.com/couchdb/quick-start.html
	2. docker版couchdb安装，使用docker-compose安装couchdb
```yaml
# couchdb.yaml
version: '2'

services:
  couchdb:
    image: hyperledger/fabric-couchdb
    ports:
    - 5984:5984
```
执行`docker-compose -f couchdb.yaml up -d`即可安装。
使用http://ip:5984/_utils即可访问couchdb的后台管理系统。


```bash
$python3 cli.py start
```
```bash
$python3 cli.py start
```

```bash
$python3 cli.py genesis_block
Genesis Wallet is: 1LYHea8NjTxaYboXJbR7LemvUZjyQc839r
```

```bash
$python3 cli.py balance 1LYHea8NjTxaYboXJbR7LemvUZjyQc839r
1LYHea8NjTxaYboXJbR7LemvUZjyQc839r balance is 1000
```

```bash
$python3 cli.py createwallet
Wallet address is 14sQYjj3n2fReJyVNoqHCmCFjNKEZAVcEB
```

```bash
python3 cli.py printwallet
Wallet are:
	19zR4zT9eSFsbSNvnQ1RCrhjN71VzPFTnH
	1MVUrxPuRgtkyLQvAoma4yEarzcMzvQqym
	18kruspe7jAbggR1sUF8fCFsZLn6efSeFk
	14sQYjj3n2fReJyVNoqHCmCFjNKEZAVcEB
```

```bash
$python3 cli.py send --from 1LYHea8NjTxaYboXJbR7LemvUZjyQc839r --to 19zR4zT9eSFsbSNvnQ1RCrhjN71VzPFTnH --amount 100
$python3 cli.py send --from 1LYHea8NjTxaYboXJbR7LemvUZjyQc839r --to 19zR4zT9eSFsbSNvnQ1RCrhjN71VzPFTnH --amount 100
```

```bash
python3 cli.py balance 1LYHea8NjTxaYboXJbR7LemvUZjyQc839r
1LYHea8NjTxaYboXJbR7LemvUZjyQc839r balance is 1900
```
