# mxqq-cloud-thost
创建属于自己的独立服务容器

---
启动脚本（run.sh/run.bat）：
---

    @echo off
    rem 运行程序


    set root=%~dp0
    set vroot=platform\runtime
    set croot=platform\config

    if not exist %vroot% ( echo dir-err:not exist platform & pause & exit )

    set root_all=%root%%vroot%\
    set root_all_c=%root%%croot%\
    echo %root_all%
    echo %root%\runtime

    java -Dloader.path=%root%runtime,%root%services -jar %root_all%jx-edp-cloud-0.0.1-SNAPSHOT.jar --spring.config.location=%root_all_c%application.yml

    pause
    exit

