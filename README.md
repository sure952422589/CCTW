## CCTW介绍
CCTW总发行量8亿枚，质押挖矿销毁6亿枚，企业链改销毁1.2亿枚，剩余8000枚作为市场流通量，销毁率90%。


## 安装节点说明
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
	CCYWY4NTViMTE0ODE3YmJkN2U4MjU0YmVlNDM1NDU
	CCZDVhMzNjYTgzNDg3MzIwMWY2YTdlOWRiODQyZGQ
	CCN2ExNDIwOGI5MmNjODkwYWQyNGNhOGJkZDljOGI
	CCNzkzY2FmMWU2NzRhMDdmNDIyMzMwNzg0OWFjOWI
```

```bash
$python3 cli.py send --from CCYWY4NTViMTE0ODE3YmJkN2U4MjU0YmVlNDM1NDU --to CCN2ExNDIwOGI5MmNjODkwYWQyNGNhOGJkZDljOGI --amount 100
$python3 cli.py send --from CCNzkzY2FmMWU2NzRhMDdmNDIyMzMwNzg0OWFjOWI --to CCMDY3MmRlM2ExNGZjYzFmYWUxZTNhYzJhOGE1MTI --amount 100
```

```bash
python3 cli.py balance CCYWY4NTViMTE0ODE3YmJkN2U4MjU0YmVlNDM1NDU
CCZDkyM2NhODM5OWRlNmI5MTNkNDhhZDdmMWNiNzk balance is 1900
```
