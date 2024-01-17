# Miniconda基础命令
> conda 用于管理多个python环境

https://openai.wiki/anaconda-and-miniconda-base-tutorial.html
## 环境
查看已安装环境
conda env list
> 其中base是一个基础环境，安装conda后默认会创建的环境，一般不使用
> *表示当前激活的环境
### 创建环境
#### arm架构
conda create --name pyname python=3.10
#### x86架构
CONDA_SUBDIR=osx-64 conda create -n crazyflie python=3.10
### 激活退出环境
conda activate (envname)
conda deactivate (envname)

### 查看安装环境依赖
conda list
conda install package name

### 删除环境
conda remove -n envname --all


# 常用命令
- conda --version
- conda update conda 更新至最新版本
- conda update --all 更新所有包
- conda update package_name
- conda remove package_name
