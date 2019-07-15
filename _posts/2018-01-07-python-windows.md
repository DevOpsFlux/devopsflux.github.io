---
layout: post
title: "Python 개발환경 설정"
subtitle:   "Windows Python 개발 환경 설정"
date: 2018-01-07 20:00:00 -0400
categories: tip
tags: python setup
---

## Windows 설치 정보
[Python 3.7.3]: https://www.python.org/downloads/release/python-373/
- Windows x86-64 executable installer

# Python 개발 환경 정보
- C:\Python\Python37\
- python version : Python 3.7.3
- pip version : pip 19.0.3 from c:\python\lib\site-packages\pip (python 3.7)
- Python 정보 관리 : D:\Python\devinfo.txt 
- Library Install 관리 : D:\Python\pip_install_list.txt 


​```python
python --version	Python 3.7.3

pip --version		pip 19.0.3 from c:\python\lib\site-packages\pip (python 3.7)
​```


## PIP 최신 버전 업그레이드
python -m pip install --upgrade pip
pip install --upgrade --trusted-host pypi.python.org

## 수동설치 방법
- 수동 설치 패키지 whl 다운로드
​```python
python -m pip install whl파일명(xxx.whl)
python -m pip install xmltodict-0.12.0-py2.py3-none-any.whl
python -m pip install beautifulsoup4-4.7.1-py3-none-any.whl
​```

### PIP로 설치가 안될경우 설치 방법
​```python
1. https://www.microsoft.com/en-us/download/details.aspx?id=44266
2. pip install -U pip
3. easy_install --upgrade pip
4. python -m pip install --upgrade pip
​```


## Python2 -> Python3
​```python
[ Python2 ]
	urllib2
	cookielib
=>
[ Python3 ]
	urllib.request
	http.cookiejar as cookielib
​```