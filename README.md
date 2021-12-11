# MongoDB-Replica
Assignment2 ทดสอบ Replica MongoDB

Step

mkdir cm_replica_demo
<br>
cd cm_replica_demo
mkdir r1
mkdir r2
mkdir r3

mongod --replSet mospito --logpath ./r1.log --dbpath ./r1 --port 27018 &
mongod --replSet mospito --logpath ./r2.log --dbpath ./r2 --port 27019 &
mongod --replSet mospito --logpath ./r3.log --dbpath ./r3 --port 27020 &


mongo --port 27018

config = {_id: "mospito", members:[
 {_id: 0, host: "localhost:27018"},
 {_id: 1, host: "localhost:27019"},
 {_id: 2, host: "localhost:27020"}]
};

rs.initiate(config);
rs.status();

mongo --host mospito/localhost:27018,localhost:27019,localhost:27020
use courses
db.getCollection('test').find({})



Link file: https://drive.google.com/drive/folders/1r4ZdqSzi29uNVtalBpll8w_YpkSexQPO?usp=sharing
PSU email Only!!
