#  WRF-Hydro <img src="https://ral.ucar.edu/sites/default/files/public/wrf_hydro_symbol_logo_2017_09_150pxby63px.png" width=100 align="left" />

## 概述
该存储库包含 Jupyter 笔记本形式的课程，重点是了解 WRF-Hydro 的基本功能。

## 需求
运行这些课程的最简单和推荐的方法是通过 [wrfhydro/training](https://hub.docker.com/r/wrfhydro/training/) Docker 容器，它预先安装了所有软件依赖项和数据。

* Docker >= v.17.12
* 网络浏览器（推荐谷歌Chrome浏览器）

### 在哪里获得帮助和/或发布问题
如果您有关于 Docker 的一般性问题，https://docs.docker.com 上有大量的在线资源，包括优秀的 Docker 文档。

如果您对 WRF-Hydro 或这些课程有任何疑问，请使用我们网站上的联系表格：https://ral.ucar.edu/projects/wrf_hydro/contact。

如果您在这些课程中发现错误，请在 https://github.com/NCAR/wrf_hydro_training/issues 的 GitHub 存储库的问题页面上记录问题。


## 如何运行
确保您已安装 Docker 并且它可以访问您的本地主机端口。 大多数接受所有默认值的开箱即用 Docker 安装都将具有此配置。

**步骤 1：打开终端或 PowerShell 会话**

**步骤 2：拉取所需代码版本的 wrfhydro/training Docker 容器**
每个训练容器都特定于 WRF-Hydro 源代码的发布版本，可在 https://github.com/NCAR/wrf_hydro_nwm_public/releases 找到。

在您的终端中输入以下命令以提取与您的代码发布版本相对应的特定培训版本。

`docker pull wrfhydro/training:v5.2.0-rc1`

**步骤 3：启动训练容器**
在终端会话中输入以下命令以启动训练 Docker 容器：

`docker run --name wrf-hydro-training -p 8888:8888 -it wrfhydro/training:v5.2.0-rc1`

**注意：如果您已经开始训练一次，则需要使用以下命令删除以前的容器：
`docker rm wrf-hydro-training`**

容器将在开始训练之前启动并执行一些操作。

1.容器会拉取模型代码
2.容器会拉取一个示例测试用例
3. 容器将启动 Jupyter Lab 服务器并将地址回显到您的终端

**注意：端口转发是使用 `-p 8888:8888` 参数设置的，它将您的 localhost 端口映射到容器端口。 如果您已经在本地主机上的端口 8888 上运行了一些东西，您将需要更改此数字**
