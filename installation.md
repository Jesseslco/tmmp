# SetUp
[参考](https://www.itread01.com/content/1546136779.html)

## 安装Oracle JDK
1. install openjdk-11
`sudo yum install java-11-openjdk-devel`

2. 配置环境变量, 注意jvm的路径可能有所不同, 可通过`which java`查看
```bash
sudo tee -a /etc/profile << 'EOF'
export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-amd64
export JRE_HOME=${JAVA_HOME}/jre
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib
export PATH=${JAVA_HOME}/bin:$PATH
EOF
```

## Install miniconda
1 安装miniconda
```bash
wget -O- https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh | bash -c 
```
2. 新增python环境
`conda create -n alipay python=3.10`

3. 安装requirements
```bash
conda activate alipay
python -m pip install -r requirements.txt
```

## Install Android Studio
1. 下载Android SDK
```bash
cd Downloads
wget https://dl.google.com/android/android-sdk_r24.2-linux.tgz
```
2. 解压
```bash
tar xvzf android-sdk_r24.2-linux.tgz
sudo mv android-sdk-linux /usr/local/Android-SDK
```
3. 配置环境变量
```bash
sudo tee -a /etc/profile << 'EOF'
export ANDROID_HOME=/usr/local/Android-SDK
export PATH=${ANDROID_HOME}/:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools:$PATH
EOF
```

4. source /etc/profile
`source /etc/profile`

5. 安装SDK
```bash
android
```
在弹出的Android SDK Manager窗口选择安装指定版本的SDK 

## 安装nodejs-lts
1. 安装nvm
`wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash`

2. 安装nodejs-lts
`nvm install --lts`

3. 安装appium
`sudo npm i -g appium`
