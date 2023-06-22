# Java mq response

```sh
docker run -e LICENSE=accept -e MQ_QMGR_NAME=QM1 -p 1414:1414 -p 9443:9443 -d --name ibmmq -e MQ_APP_PASSWORD=passw0rd ibmcom/mq
```

https://localhost:9443/ibmmq/console/login.html#

- admin
- passw0rd

- Colas temporales

setmqaut -m QM1 -n SYSTEM.DEFAULT.MODEL.QUEUE -t queue -p app +get +put +inq +dsp

```sh
docker container exec -it ibmmq setmqaut -m QM1 -n SYSTEM.DEFAULT.MODEL.QUEUE -t queue -p app +get +put +inq +dsp
```

```sh
docker container exec -it ibmmq sh
/opt/mqm/samp/bin/amqsgetc DEV.QUEUE.1 QM1
```