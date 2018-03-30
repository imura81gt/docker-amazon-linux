Overview
============================

start-up Amazon Linux & Amazon Linux 2
----------------------------


```
$ docker-compose up
```

```
Creating network "dockeramazonlinux_default" with the default driver
Building amazonlinux
Step 1/3 : FROM amazonlinux:1
 ---> 3faa54d46dec
Step 2/3 : RUN yum install -y cowsay
 ---> Using cache
 ---> 2c308616cc9e
Step 3/3 : CMD cat /etc/system-release | cowsay
 ---> Using cache
 ---> cc1ddf7fe41e
Successfully built cc1ddf7fe41e
Successfully tagged dockeramazonlinux_amazonlinux:latest
WARNING: Image for service amazonlinux was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
Building amazonlinux2
Step 1/3 : FROM amazonlinux:2
 ---> c15deadb6ec1
Step 2/3 : RUN yum install -y cowsay
 ---> Using cache
 ---> 7d2ca63849a9
Step 3/3 : CMD cat /etc/system-release | cowsay
 ---> Using cache
 ---> a41e02511dea
Successfully built a41e02511dea
Successfully tagged dockeramazonlinux_amazonlinux2:latest
WARNING: Image for service amazonlinux2 was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
Creating dockeramazonlinux_amazonlinux_1  ... done
Creating dockeramazonlinux_amazonlinux2_1 ... done
Attaching to dockeramazonlinux_amazonlinux_1, dockeramazonlinux_amazonlinux2_1
amazonlinux_1   |  __________________________________
amazonlinux_1   | < Amazon Linux AMI release 2017.09 >
amazonlinux_1   |  ----------------------------------
amazonlinux_1   |         \   ^__^
amazonlinux_1   |          \  (oo)\_______
amazonlinux_1   |             (__)\       )\/\
amazonlinux_1   |                 ||----w |
amazonlinux_1   |                 ||     ||
amazonlinux2_1  |  ______________________________________
amazonlinux2_1  | / Amazon Linux release 2 (2017.12) LTS \
amazonlinux2_1  | \ Release Candidate                    /
amazonlinux2_1  |  --------------------------------------
amazonlinux2_1  |         \   ^__^
amazonlinux2_1  |          \  (oo)\_______
amazonlinux2_1  |             (__)\       )\/\
amazonlinux2_1  |                 ||----w |
amazonlinux2_1  |                 ||     ||
dockeramazonlinux_amazonlinux_1 exited with code 0
dockeramazonlinux_amazonlinux2_1 exited with code 0
```

Usages
============================

checking yum repo
----------------------------

```
$ docker-compose run amazonlinux yum info logrotate
Loaded plugins: ovl, priorities
Available Packages
Name        : logrotate
Arch        : x86_64
Version     : 3.7.8
Release     : 26.14.amzn1
Size        : 62 k
Repo        : amzn-main/latest
Summary     : Rotates, compresses, removes and mails system log files
URL         : https://fedorahosted.org/logrotate/
License     : GPL+
Description : The logrotate utility is designed to simplify the administration of
            : log files on a system which generates a lot of log files.  Logrotate
            : allows for the automatic rotation compression, removal and mailing of
            : log files.  Logrotate can be set to handle a log file daily, weekly,
            : monthly or when the log file gets to a certain size.  Normally,
            : logrotate runs as a daily cron job.
            :
            : Install the logrotate package if you need a utility to deal with the
            : log files on your system.

$
```

```
$ docker-compose run amazonlinux2 yum info logrotate
Loaded plugins: ovl, priorities
Available Packages
Name        : logrotate
Arch        : x86_64
Version     : 3.8.6
Release     : 14.amzn2
Size        : 69 k
Repo        : amzn2-core/2017.12/x86_64
Summary     : Rotates, compresses, removes and mails system log files
URL         : https://fedorahosted.org/logrotate/
License     : GPL+
Description : The logrotate utility is designed to simplify the administration of
            : log files on a system which generates a lot of log files.  Logrotate
            : allows for the automatic rotation compression, removal and mailing of
            : log files.  Logrotate can be set to handle a log file daily, weekly,
            : monthly or when the log file gets to a certain size.  Normally,
            : logrotate runs as a daily cron job.
            :
            : Install the logrotate package if you need a utility to deal with the
            : log files on your system.

$
```
