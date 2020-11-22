# 环境配置
## 一、Blade构建系统配置
1. python环境
```
rm /usr/bin/python
ln -s /usr/bin/python3.x /usr/bin/python
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
3. 安装blade
```
git clone https://github.com/chen3feng/blade-build.git
cd blade-build
./install
```
如果报``./install: 行 32: ~/.profile: 没有那个文件或目录``

```
 source ~/.profile
```
4. 报ninja错误
安装ninja

5. git安装blade在使用thirdparty时报``hrds``错误

在git blade库中找到relese blade-1.1.2
``https://github.com/chen3feng/blade-build/releases/tag/1.1.2``
下载1.1.2安装包，安装。