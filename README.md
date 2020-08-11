# fabric-on-k8s

## 部署
namespace默认default
组织关系、证书配置configtx.yaml、crypto-config.yaml，工具在bin目录（1.4版本）
kebernetes资源文件docker目录

## 说明
使用的是 zk+kafka 集群, 3个 zk pod statefulset 方式部署，对外提供 headless service 接口，4个 kafka service，1个 orderer service，3个 peer service，对应的都是 deployment 的部署方式
集群配置pvc数据持久化
coredns （configmap）配置域名重定向：
rewrite name peer0.org1.example.com peer0-org1.default.svc.cluster.local
rewrite name peer0.org2.example.com peer0-org2.default.svc.cluster.local
rewrite name peer0.org3.example.com peer0-org3.default.svc.cluster.local

