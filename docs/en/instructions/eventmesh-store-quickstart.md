# Eventmesh-store Quick start Instruction

### dependencies
```
64bit OS, Linux/Unix is recommended;
64bit JDK 1.8+;
Gradle at least 5.6;
4g+ free disk for eventmesh-store server
```

### download and build with sources

download source code from [https://github.com/WeBankFinTech/EventMesh](https://github.com/WeBankFinTech/EventMesh)  
You will get 'EventMesh-master.zip'  

**build eventmesh-store**  
The eventmesh-store takes DeFiBus for example at the follwing parts, because eventmesh depends on defibus as store layer by default, other implements such as Rocketmq etc. is coming soon.  

```
unzip EventMesh-master.zip
cd /*YOUR DEPLOY PATH*/EventMesh-master/eventmesh-store
gradle clean dist tar -x test
```
You will get **eventmesh-store_1.0.0.tar.gz** in directory /* YOUR DEPLOY PATH */EventMesh-master/eventmesh-store/build

### Deployment

- deploy DeFiBusNamesrv  
```
upload eventmesh-store_1.0.0.tar.gz
tar -zxvf eventmesh-store_1.0.0.tar.gz
cd bin
sh runnamesrv.sh
```
If you see "Thre Name Server boot success" in ../logs/namesrv.log, you setup DeFiBus Namesrv successfully.

- deploy DeFiBusBroker
```
upload eventmesh-store_1.0.0.tar.gz
tar -zxvf eventmesh-store_1.0.0.tar.gz
cd conf
config your broker.properties
cd ../bin
sh runbroker.sh
```
If you see "The broker \[YOUR-BROKER-NAME, IP:PORT\] boot success." in ../logs/broker.log, you setup eventmesh-store successfully.

