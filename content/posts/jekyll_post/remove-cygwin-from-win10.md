---
categories:
  - notes
comments: true
date: 2021-08-17
description: remove cygwin from windows10
tags:
  - cygwin
  - gcc
title: How to completely uninstall/remove cygwin from windows10
url: /2021/08/17/remove-cygwin-from-win10/
---


## Steps for removal

1. open powershell with administrator privilege.

2. run `takeown /f PATH_TO_CYGWIN /r /d y`, for me, PATH_TO_CYGWIN = C:\ENVs\MinGW64.

3. run `icacls PATH_TO_CYGWIN /t /grant everyone:F`

4. run `del PATH_TO_CYGWIN`.

5. check if the files are deleted and delete the residual files. 