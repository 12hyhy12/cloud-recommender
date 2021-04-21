# cloud-recommender
* 2017YFB1400804 <br>
A simple recommender system of  AWS cloud configuration for Spark and Hadoop applications <br>
这是个为Spark和Hadoop应用推荐亚马逊云服务器配置的系统。该系统可以从18种亚马逊云主机种为32种应用推荐最佳机型。<br>

## 技术架构 <br>
![the text displayed while lost the image](https://github.com/12hyhy12/cloud-recommender/blob/main/pic/1.png) 
<br>
前端界面使用VUE编写，向后端发送应用信息。后端框架使用flask，使用基于scout数据集训练的随机森林模型预测最佳机型。<br>

## 技术特色 <br>
使用echarts库对随机森林模型进行可视化。<br>

## 部署方式 <br>
需要使用kubeadm安装kubernetes。<br>
前端依赖kubernetes-admin。demo\vmrec需要放在\kubernetes-admin\src\views下，执行<br>
```
npm install
npm run dev
```
后端执行<br>
```
cd /demo/platform/f
docker build -t cfgrec .
cd ..
kubectl apply -f service.yaml
kubectl apply -f node.yaml
```

## 使用说明 <br>
在前端输入应用信息后可以获取推荐结果和随机森林模型推理过程。