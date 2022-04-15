# saas-flutter

## 1、安装软件

- 显示隐藏文件
```
defaults write com.apple.finder AppleShowAllFiles -boolean true ; killall Finder
```

- ohmyzsh

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

```

- brew
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

brew install visual-studio-code

brew install imagemagick

brew install openjdk@8

brew install curl-openssl
```

- Android SDK（commandlinetools-mac-7583922_latest）

下载网站下载 **Command line tools**
```
https://developer.android.com/studio 
```
解压缩到 **～/opt/Android/sdk/** 目录为 **cmdline-tools/latest**

国内使用

```
./sdkmanager --proxy_host=sdk.gdgshanghai.com --proxy_port=8000 --proxy=http --no_https "platform-tools" "build-tools;30.0.3" "build-tools;28.0.3" "build-tools;29.0.2" "platforms;android-30" "platforms;android-29" "platforms;android-28"
```

国外使用
```
sdkmanager "platform-tools" "build-tools;30.0.3" "build-tools;28.0.3" "build-tools;29.0.2" "platforms;android-30" "platforms;android-29" "platforms;android-28"
```

- 安装 Flutter

https://github.com/dashixiong91/fvm

```

brew tap dashixiong91/fvm

brew install fvm

```
**配置 .zshrc**
```
code ~/.zshrc
source ~/.zshrc
```

安装 flutter 1.22.6

```
fvm install 1.22.6
fvm use 1.22.6

flutter doctor
flutter doctor --android-licenses
```

## 2、Clone 代码


### Git（Fork）

```
https://fork.dev/
```

### 配置 拷贝 ssh 到 ~/.ssh/
ssh.zip 
解压密码：chenyue

### 配置 ssh config
code ~/.ssh/config
```
Host code.aliyun.com
IdentityFile ~/.ssh/id_rsa_new
```

### clone 下面代码
```
git@code.aliyun.com:Mexico2/mf_mexico.git
```

## 3、获取签名

证书指纹
```
keytool -v -list -keystore sign/keystore.jks -storepass $KEY_PASSWORD
```

密钥散列
```
keytool -exportcert -alias keystore -keystore sign/keystore.jks -storepass $KEY_PASSWORD | openssl sha1 -binary | openssl base64
```

## 4、Windows 特供

- 环境变量

```
C:\Python27\;C:\Python27\Scripts;%JAVA_HOME%\bin;.;C:\Program Files\ImageMagick-7.1.0-Q16-HDRI;%SystemRoot%\system32;%SystemRoot%;%SystemRoot%\System32\Wbem;%SYSTEMROOT%\System32\WindowsPowerShell\v1.0\;C:\Program Files\Microsoft VS Code\bin;C:\Program Files\Git\cmd;%ANDROID_SDK_ROOT%\cmdline-tools\latest\bin;%FLUTTER%\bin;C:\Users\Administrator\AppData\Local\Fork\gitInstance\2.30.2\mingw64\bin;%FLUTTER%\bin\cache\dart-sdk\bin

ANDROID_SDK_ROOT=C:\sdk

FLUTTER=C:\flutter\flutter_windows_2.5.3-stable

```
- openjdk 11
```
https://adoptium.net/?variant=openjdk11
```
- magick
```
https://imagemagick.org/index.php
```

## 配置参考

- .zshrc

```
plugins=(
    git
    flutter
    zsh-autosuggestions
)


export JAVA_HOME=/usr/local/opt/openjdk@8
export PATH="$JAVA_HOME/bin:$PATH"

# 国内使用
# export PUB_HOSTED_URL=https://pub.flutter-io.cn
# export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn

export FLUTTER_STORAGE_BASE_URL=https://storage.googleapis.com
export PUB_HOSTED_URL=https://pub.dev

export PUB_CACHE="$HOME/.pub-cache"


export FVM_DIR="$HOME/.fvm"
source "/usr/local/opt/fvm/init.sh"

export PATH=$FVM_DIR/current/bin:$PATH
export PATH=$FVM_DIR/current/bin/cache/dart-sdk/bin:$PATH

export GIT_SSL_NO_VERIFY=true

export NO_PROXY=localhost,127.0.0.1
# 国内使用
# export HTTP_PROXY=127.0.0.1:10087


export PATH="$PATH":"$HOME/.pub-cache/bin"
export ANDROID_SDK_ROOT="$HOME/opt/Android/sdk"
export PATH="$ANDROID_SDK_ROOT/cmdline-tools/latest/bin:$PATH"
export PATH="$ANDROID_SDK_ROOT/platform-tools:$PATH"
export PATH="$ANDROID_SDK_ROOT/tools/:$PATH"

```

- Command_Line_Tools（Command_Line_Tools_for_Xcode_11.5） 国内自动安装失败需要
