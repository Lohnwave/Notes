# 环境配置
## 一、Blade构建系统配置
1. python环境
```
rm /usr/bin/python
ln -s /usr/bin/python3.x /usr/bin/python
```
Mac
```
nano ~/.bash_profile
# 在行尾添加
alias python=python3
# 退出
source ~/.bash_profile
```
2. 安装scons
```
sudo apt install scons
```
或者
```
wget http://prdownloads.sourceforge.net/scons/scons-4.0.1.tar.gz
tar -xf scons-4.0.1.tar.gz
sudo python3 scons-4.0.1/setup.py install
```
或者
##blade build 报错 `except IOError, ex_value:`scons版本问题，安装python2-scons
```
# python2-scons
wget http://prdownloads.sourceforge.net/scons/scons-3.1.2.tar.gz
cd scons-3.1.2
python bootstrap.py build/scons
python build/scons/setup.py install

```
3. 安装devtoolset8
```
sudo/brew install/yum install devtoolset-8-toolchain
./opt/rh/devtoolset-8/enable #把这个加到～/.bash_profile
```
4. 安装blade
```
git clone https://github.com/chen3feng/blade-build.git
cd blade-build
./install
```
如果报``./install: 行 32: ~/.profile: 没有那个文件或目录``

```
 source ~/.profile
```
5. 报ninja错误
安装ninja

6. git安装blade在使用thirdparty时报``hrds``错误

在git blade库中找到relese blade-1.1.2
``https://github.com/chen3feng/blade-build/releases/tag/1.1.2``
下载1.1.2安装包，安装。
谷歌源
``https://code.google.com/archive/p/typhoon-blade/downloads``
