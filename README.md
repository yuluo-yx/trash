# 环境配置

> **步骤说明**
>
> 1. 安装 python 3.11 版本
> 2. 安装对应的 cuda 和 cudnn (版本要求对应)。
> 3. 安装参考：https://blog.csdn.net/anmin8888/article/details/127910084
> 4. 安装 pycharm
> 5. 安装 pytorch
> 6. 安装 jupyter
>
> **硬件条件**
>
> 独立显卡，必须有 GPU，CPU 训练速度过慢。
>
> 内存 16 G+
>
> CPU i7+
>
> **linux 服务器系统同样配置！**

## 安装 cuda

> cmd 输入 nvidia-smi 查看 显卡信息

```shell
  Administrator@yuluo-laptop ~ ❯❯❯ nvidia-smi
Tue Mar 12 20:52:14 2024
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 527.37       Driver Version: 527.37       CUDA Version: 12.0     |
|-------------------------------+----------------------+----------------------+
| GPU  Name            TCC/WDDM | Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|                               |                      |               MIG M. |
|===============================+======================+======================|
|   0  NVIDIA GeForce ... WDDM  | 00000000:01:00.0 Off |                  N/A |
| N/A   54C    P0    N/A /  N/A |    109MiB /  3072MiB |      1%      Default |
|                               |                      |                  N/A |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                                  |
|  GPU   GI   CI        PID   Type   Process name                  GPU Memory |
|        ID   ID                                                   Usage      |
|=============================================================================|
|    0   N/A  N/A       840    C+G   C:\Windows\System32\dwm.exe     N/A      |
|    0   N/A  N/A      8460    C+G   ...n1h2txyewy\SearchHost.exe    N/A      |
|    0   N/A  N/A      8468    C+G   ...artMenuExperienceHost.exe    N/A      |
|    0   N/A  N/A     10024    C+G   ...2txyewy\TextInputHost.exe    N/A      |
|    0   N/A  N/A     11344    C+G   ...Files\Tencent\QQNT\QQ.exe    N/A      |
|    0   N/A  N/A     12168    C+G   ...d\runtime\WeChatAppEx.exe    N/A      |
|    0   N/A  N/A     12372    C+G   ...Z32DMXSOKTFGNNQ\DeepL.exe    N/A      |
|    0   N/A  N/A     13668    C+G   ...8bbwe\WindowsTerminal.exe    N/A      |
|    0   N/A  N/A     18244    C+G   ... 2023.2\bin\pycharm64.exe    N/A      |
+-----------------------------------------------------------------------------+
  Administrator@yuluo-laptop ~ ❯❯❯
```

查看 `CUDA Version` 下载对应的 CUDA 安装。

下载地址：https://developer.nvidia.com/cuda-toolkit-archive

## 下载 cudnn

> cudnn 是 cuda 的增强工具，提供张量计算能力。
>
> **安装需要和 cuda 版本对应**

下载地址：https://developer.nvidia.com/rdp/cudnn-archive#a-collapse897-120

验证步骤参考开头第三步链接。

## 安装 pycharm

> pycharm: python 的集成开发工具。
>
> **破解方法百度，尽量不要使用社区版，功能有阉割**

下载地址：https://www.jetbrains.com/pycharm/

## 安装 pytorch

地址：https://pytorch.org/get-started/locally/

选择条件之后复制命令安装。如果安装过慢，使用代理

```python
Administrator@yuluo-laptop ~ ❯❯❯ pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121 --proxy=127.0.0.1:7890
```

## 安装 jupyter

推荐在创建 python 的 虚拟环境，依赖隔离进行，避免版本干扰问题。

## 检查环境

```shell
# python
python --version
# cuda
nvcc -V
```

## 运行

运行 jupyter book 内的代码即可。

注意：如果运行失败，显示 GPU 内存超出，可以将 batch_size 参数调小来训练模型。

