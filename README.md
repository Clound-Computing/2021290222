# 2021290222
How well apply simply MLP to IUR task?
## 环境配置
### 下载库
最重要的配置如下：
- pytorch >= 1.2.0 (not tested on other versions, but 1.0.0 may work though)
- allennlp == 0.9.0

其他依赖库输入此指令下载：

```console
pip install -r requirement.txt
```
## 数据

### 准备数据集

论文给的数据集叫Multi，在'/dataset/Multi/'目录下输入 `.\download.sh` 可以下载
我给的数据集叫GossipCopIUR，在'/dataset/Gossipcop_IUR/GossipcopIUR.txt'

## 训练

可以使用 `src` 文件夹下的'train_multi.sh'来训练:

```console
./train_multi.sh
```

## 评估
在'src'目录下输入指令来查看原数据集的评价，生成的数据在目录'../pretrained_weights/multi/model.tar.gz.json'
```concolse
python evaluate.py --model_file ../pretrained_weights/multi/model.tar.gz --test_file ../dataset/Multi/test.txt
```
在'src'目录下输入指令来查看新数据集的评价，生成的数据在目录'../pretrained_weights/GossipcopIUR/model.tar.gz.json'
```concolse
python evaluate.py --model_file ../pretrained_weights/GossipcopIUR/model.tar.gz --test_file ../dataset/Gossipcop_IUR/GossipcopIUR.txt
```

## 下载预训练模型
| Dataset | Config | Pretrained_Weights |
| :---: | :---: | :---: |
| Multi (Restoration-200K) | multi.jsonnet | [multi.tar.gz](https://drive.google.com/file/d/1uRrbpqOw1Nga1maSnX0gWF1kSp0ncB48/view?usp=share_link) |
GossipcopIUR用同一个模型，但是要放在'../pretrained_weights/GossipcopIUR/'目录下

### Acknowledgement

We refer to the code of [RUN](https://github.com/microsoft/ContextualSP/tree/master/incomplete_utterance_rewriting). Thanks for their contributions.
