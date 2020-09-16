#坑 调试时间 1.5 天

1. 数据库自己安装，不然会一直报错，且只支持postgre数据库
2. 写value模板的时候记得切换到最新的1.4.0分支,master分支的不管用
3. 请使用静态的pv-pvc，动态的不管用，也不好管理
4. 安装命令：
   kubectl create namespace harbor-server
   # 安装db
   kubectl apply -f harbor-db.yaml -n harbor-server
   # 安装pv-pvc
   kubectl apply -f storage.yaml -n harbor-server
   # 根据覆盖配置安装harbor相关组件
   helm install harbor-server  harbor/harbor --values value.yaml  -n harbor-server 

