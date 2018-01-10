#Ztool 命令使用手册

[TOC]

##安装

打开终端，执行如下命令：

>$ git clone https://github.com/peter-m-shi/ztool.git $HOME/ztool;sh $HOME/ztool/setup.sh



##gitf工具##

gitf工具包含了如下几个命令：



**gif feature**（亦可简写为**ff**）



功能：



（1）从develop拉取feature分支，开始工作；

（2）完成开发，合并回原分支.



示例：



>$ ==ff== function1 ==go==



>$ ==ff== function1 ==ok==



Notes:

（1）根据提示选择从develop，develop-A，develop-B拉取分支。

（2）上述命令中的"function1"为feature分支名。





**gif release**（亦可简写为**fr**）



功能：



（1）从develop拉取release分支，开始集成测试；

（2）完成测试，合并到master分支（并打tag）和develop分支。



示例：



>$ ==fr== 7.0.0 ==go==

>$ ==fr== 7.0.0 ==ok==



Notes：上述命令中的"7.0.0"为待发布版本号。



**gif bugfix**（亦可简写为**fb**）



功能：



（1）从release拉取bugfix分支，修复bug；

（2）完成修复，合并回release分支。



示例：



> $ ==fb== MGV6-1234 ==go==



> $ ==fb== MGV6-1234 ==ok==



Notes：上述命令中的“MGV6-1234”为BugID.



**gif hotfix**（亦可简写为**fh**）



功能：



（1）从master拉取hotfix分支，开始修复线上bug；

（2）完成修复，合并回master分支。



示例：



>$ ==fh== crash ==go==



>$ ==fh== crash ==ok==





##gitz工具##

gitz工具集的使用场景：多人协作于同一分支（协作开发同一feature、sub-feature，协作修改同一bugfix，hotfix）



**gitz pull**



从当前personal分支的上级分支拉取更新



**gitz push**



向当前personal分支的上级分支合并修改



**gitz request**



直接在命令行页面提起pull request，不需要打开Bitbucket创建pull request，提请成功会出现弹窗提示。



**git sub**



从上级分支切换到personal分支



**git super**



从当前的personal分支切换到上级分支



**git remove**



从本地和远程移除名为XXX的分支

