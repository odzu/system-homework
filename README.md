# Hummingbird Benchmarks 

本文件夹中包含报告中提及的所有实验，要重复实验请按以下步骤进行：

安装Pytorch、Xgboost、LightGBM、Sklearn、ONNX、TVM

```
pip install torch
pip install xgboost
pip install lightgbm
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple onnx
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple onnxruntime
pip install scikit-learn
pip isntall tvm(推荐参考官网使用sudo安装完整包)
```
接着安装HUMMINGBIRD：
```
python -m pip install hummingbird-ml
```

注意，如运行遇任何hummingbird依赖包的报错，多是由版本不兼容导致，可进入`/home/user/anaconda3/envs/bird/lib/python3.8/site-packages/hummingbird`或`/home/user/anaconda3/envs/bird/lib/python3.8/site-packages/benchmark`目录中对报错文件进行修改，为便于debug，本文将已进行过修改的安装包同步更新于目录`sitepackages`，可按需查找其中文件替换依赖包中文件。

完成安装后，可进入benchmark文件夹实现所有实验：
```
cd benchmarks
```

接着，在trees文件夹中实现trees的实验：
```
cd trees
# CPU
python run.py -dataset covtype,epsilon,higgs
# GPU
python run.py -dataset covtype,epsilon,higgs -gpu -batch_benchmark
```
上述过程会自动下载数据集，若无法下载完整数据集，可从以下链接手动下载放在datasets文件夹下对应名称文件夹内：

[covtype](https://archive.ics.uci.edu/ml/datasets/covertype)

[epsilon](https://www.csie.ntu.edu.tw/~cjlin/libsvmtools/datasets/binary.html)

[higgs](https://archive.ics.uci.edu/ml/datasets/HIGGS)

本文的实验数据可从trees目录下找到：
```
# 表2 & 表5
result-6-500-8-10000-c_e.json
result-6-500-8-10000-h.json
# 表4
result-gpu-500-8-10000c.json
result-gpu-500-8-10000e.json
result-gpu-500-8-10000h.json
```

可在operators文件夹中实现其它操作符的实验：
```
cd operators
# CPU
python run.py 
# GPU
python run.py -gpu 
```
本文的实验数据可从operators目录下找到：
```
# 表6
result-cpu-1000000.json
result-gpu-1000000.json
```



