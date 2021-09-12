# 1. 启动docker

## 1.1 修改datagen写入kafka的速度

```yml
  datagen:
    command: "省略前面的命令 --speedup 改这里默认3000"
```

## 1.2 docker compose启动

```bash
docker compose up -d
```

## 1.3 检查下kafka的数据

消费10条记录看下

```bash
docker-compose exec kafka bash -c 'kafka-console-consumer.sh --topic user_behavior --bootstrap-server kafka:9094 --from-beginning --max-messages 10'
```

## 1.4 检查kibana启动情况

打开[http://localhost:5601/](http://localhost:5601/)看下kibana的界面

## 1.5 进入sql cli

```bash
docker-compose exec sql-client ./sql-client.sh
```

# 2. create table