# Appium Install Guide


[TOC]


## 1. Appium 실행을 위한 필수 프로그램 설치 및 환경변수 설정

#### 1) Oracle-Java8-Installer install
###### * for Linux
```
$ sudo add-apt-repository ppa:webupd8team/java
$ sudo apt-get update

# XXX. skip - works w/o it
# sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys   xxxxxxxx(pubkey)

$ sudo apt-get install oracle-java8-installer

# java version check
$ java -version
```

###### * for Mac osx
```
# NOTE - osx check java version before installation.

$ brew cask install caskroom/cask/java

# java version check
$ java -version
```


#### 2) Android-sdk install
###### * for Linux
```
# for linux:

$ sudo apt-get install android-sdk
$ sudo ln -s  /usr/lib/android-sdk /opt/android-sdk
```

###### * for Mac osx
```
$ brew cask install caskroom/cask/android-sdk
```


#### 3) edit Environment Variable PATH  ($JAVA_HOME, $ANDROID_HOME)
###### * for Linux
```
# 환경변수 추가
$ vi ~/.bashrc

export JAVA_HOME=/usr/lib/jvm/java-8-oracle
export ANDROID_HOME=/opt/android-sdk
export PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools

# 저장후 내용 적용
$ source ~/.bashrc
```

###### * for Mac osx
```
# 환경변수 추가
$  vi ~/.bash_profile

export JAVA_HOME=$(/usr/libexec/java_home)
export ANDROID_HOME=/usr/local/share/android-sdk
export PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools

# 저장후 내용 적용
$ . ~/.bash_profile
```


#### 4) Nodejs, npm install
###### * Linux
```
$ sudo apt-get install nodejs-legacy npm

# node version check
$ node -v
>> 4.2.6
$ npm -v
>> 3.x.x

[npm global permission setting]
$ mkdir ~/.npm-global
$ npm config set prefix '~/.npm-global'

$ vi ~/.profile
# 아래 코드 추가 후 저장
export PATH=$PATH:~/.npm-global/bin

# 저장한 내용 적용
$ source ~/.profile
```

###### * Mac osx
```
$ brew install node npm

# node version check
$ node -v
>> v8.3.0
$ npm -v
5.3.0

[npm global permission setting]
$ mkdir ~/.npm-global
$ npm config set prefix '~/.npm-global'

$ vi ~/.bash_profile
# 아래 코드 추가 후 저장
export PATH=$PATH:~/.npm-global/bin

# 저장한 내용 적용
$ . ~/.bash_profile
```





## 2. Appium install

#### 2.0 Appium Install

```
$ brew install node      # get node.js
$ npm install -g appium  # get appium
$ npm install wd         # get appium client
$ appium &               # start appium
```

#### 2.1 Appium Github Clone
Link : [https://github.com/appium/appium]

1) Download Appium source into your PC
```
$ git clone https://github.com/appium/appium.git﻿﻿

$ cd appium
```


2) NPM Install
```
$ npm install
```

3) Run Appium [ node .(dot) ]
```
$ node .
# If you see following messages, Appium started successfully.
[Appium] Welcome to Appium v1.7.0-beta (REV cf24a80809309fb5467099e570cddd256cacbb28)
[Ap﻿pium] Appium REST http interface listener started on 0.0.0.0:4723
```

```
# Error Case 1 :
module.js:491
    throw err;
    ^

Error: Cannot find module '/Users/han/Documents/appium-1.6.5'
    at Function.Module._resolveFilename (module.js:489:15)
    at Function.Module._load (module.js:439:25)
    at Function.Module.runMain (module.js:609:10)
    at startup (bootstrap_node.js:158:16)
    at bootstrap_node.js:598:3

# Error Case 2 :
npm install 실행 후 Appium 프로젝트 폴더에 build 라는 폴더가 있는지 확인 없을 경우 다음 명령줄 실행

# Resolve
$ sudo xcode-select --switch /Library/Developer/CommandLineTools
```



#### 2.2 Appium Github Release Download
Link : [https://github.com/appium/appium/releases]

1) 위 링크에서 원하는 버전의 Appium 압축 파일 다운로드

2) Extract Appium
```
$ cd PATH/TO/DOWNLOAD/FOLDER

# tar.gz Extract
$ tar -zxvf appium-1.6.x.tar.gz TARGET/PATH

ex) tar -zxvf appium-1.6.3.tar.gz ~/Documents/appium-1.6.3
```

3) 해당 폴더로 이동

```
$ cd appium-1.6.3
```

4) NPM Install

```
$ npm install
```

5) Run Appium [ node .(dot) ]

```
$ node .
```

#### 2.3 Appium Desktop Download
Link : [http://appium.io/]

1) 위 링크로 이동

2) Download Appium 을 통해 Appium Desktop download 페이지로 이동

3) Appium Desktop 파일 다운 로드 후 실행
