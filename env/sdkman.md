# sdk常用指令

> sdkman 用于管理多版本java，maven，gradle等
 
## 创建删除查看环境
- 安装最新稳定版jdk
``` $ sdk install java```
会提示是否将此版本设置为默认版本

*  安装特定版本
```$ sdk install scala 3.3.1```

- 删除版本
```$ sdk uninstall scala 3.3.1 ```

* List Candidates
``` $ sdk list ```

- List Versions
```$ sdk list java ```
列出可安装，本地，已经安装的版本

* 临时切换版本
```$ sdk use scala 3.3.1```

- 切换默认版本
``` $ sdk default scala 3.3.1```

* 查看当前版本
```
$ sdk current java
$ sdk current
```

## 环境指令
通过在项目根目录.sdkmanrc实现不同项目使用不同环境，该文件可以通过如下指令自动创建：

```$ sdk env init```
会在当前文件夹创建配置文件
```
\# Enable auto-env through the sdkman_auto_env config
\# Add key=value pairs of SDKs to use below
java=21.0.1-tem
```
The file is pre-populated with the current JDK version in use, but can contain as many key-value pairs of supported SDKs as needed. To switch to the configuration present in your .sdkmanrc file, simply issue the following command:
```sdk env```
You should see output that looks something like this:
```Using java version 21.0.1-tem in this shell.```
Your path has now also been updated to use any of these SDKs in your current shell. When leaving a project, you may want to reset the SDKs to their default version. This can be achieved by entering:

```
$ sdk env clear
Restored java version to 21.0.1-tem (default)
```
                    
After checking out a new project, you may be missing some SDKs specified in the project's .sdkmanrc file. To install these missing SDKs, just type:

```$ sdk env install ``` 
Do you want to switch SDK versions automatically when you cd into a directory? This can be done by setting the sdkman_auto_env=true in the SDKMAN configuration. Note that this will also reset any project-specific SDKs to their default version when leaving the directory.

## 版本升级

``` 
$ sdk upgrade springboot
$ sdk upgrade
```

- sdk版本
```$ sdk version```
* 离线模式
```
$ sdk offline enable
Forced offline mode enabled.
$ sdk offline disable
Online mode re-enabled!
```
离线模式，部分指令功能scaled down capacity

- 获取环境地址
```$ sdk home java 21.0.1-tem```



## 配置
~/.sdkman/etc/config 文件保存sdk配置，可以通过如下指令修改配置

```
\# make sdkman non-interactive, preferred for CI environments
sdkman_auto_answer=true|false

\# check for newer versions and prompt for update
sdkman_selfupdate_feature=true|false

\# disables SSL certificate verification
\# https://github.com/sdkman/sdkman-cli/issues/327
\# HERE BE DRAGONS....
sdkman_insecure_ssl=true|false

\# configure curl timeouts
sdkman_curl_connect_timeout=5
sdkman_curl_continue=true
sdkman_curl_max_time=10

\# subscribe to the beta channel
sdkman_beta_channel=true|false

\# enable verbose debugging
sdkman_debug_mode=true|false

\# enable colour mode
sdkman_colour_enable=true|false

\# enable automatic env
sdkman_auto_env=true|false

\# enable bash or zsh auto-completion
sdkman_auto_complete=true|false
```