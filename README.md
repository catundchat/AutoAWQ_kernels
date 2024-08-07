# AutoAWQ Kernels

win10系统上不用wsl2的方法：
- 配置好对应torch等环境，我的win10系统上为
torch==2.0.1+cu118
torchaudio==2.0.2+cu118
torchvision==0.15.2+cu118
- `git clone https://github.com/catundchat/AutoAWQ_kernels.git`下载
- `git install -e .`即可安装autoawq_kernels实现推理加速效果

安装完后`pip list`能看到`autoawq==0.2.4
-e git+https://github.com/casper-hansen/AutoAWQ_kernels@83d1f4b326a9067d0f94f089ef1bb47cf5377134#egg=autoawq_kernels
`即为安装成功，可以在windows上通过awq kernel加速。


AutoAWQ Kernels is a new package that is split up from the [main repository](https://github.com/casper-hansen/AutoAWQ) in order to avoid compilation times.

## Requirements

- Windows: Must use WSL2.

- NVIDIA:
  - GPU: Must be compute capability 7.5 or higher.
  - CUDA Toolkit: Must be 11.8 or higher.
- AMD:
  - ROCm: Must be 5.6 or higher.

## Install

### Install from PyPi

The package is available on PyPi with CUDA 12.1.1 wheels:

```
pip install autoawq-kernels
```

### Install release wheels

For ROCm and other CUDA versions, you can use the wheels published at each [release](https://github.com/casper-hansen/AutoAWQ_kernels/releases/):

```
pip install https://github.com/casper-hansen/AutoAWQ_kernels/releases/download/v0.0.2/autoawq_kernels-0.0.2+rocm561-cp310-cp310-linux_x86_64.whl
```

### Build from source
You can also build from source:

```
git clone https://github.com/casper-hansen/AutoAWQ_kernels
cd AutoAWQ_kernels
pip install -e .
```

To build for ROCm, you need to first install the following packages `rocsparse-dev hipsparse-dev rocthrust-dev rocblas-dev hipblas-dev`.
