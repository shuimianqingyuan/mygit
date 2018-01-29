# Reference for Ztool
## gitf命令集
### gitf feature
- ```gitf feature [分支名] go```亦可直接输入```ff [分支名] go```:开始一个新的feature。
- ```gif feature [分支名] pr```亦可直接输入```ff [分支名] pr```：提pull request到develop。
- ```gif feature [分支名] ok```亦可直接输入```ff [分支名] ok```：合并feature到develop，同时删除该feature。
- 示例：
```
$ ff IOS-9-pageRefactor go
$ ff IOS-9-pageRefactor pr
$ ff IOS-9-pageRefactor ok
```

### gitf bugfix
- ```gif bugfix [分支名] go```亦可直接输入```fb [分支名] go```：开始一个新的bugfix。
- ```gif bugfix [分支名] pr```亦可直接输入```fb [分支名] pr```：提交pull request到develop或release。
- ```gif bugfix [分支名] ok```亦可直接输入```fb [分支名] ok```：合并bugfix到develop或release，同时删除该bugfix。
- 示例：
```
$ fb MGV5-20538-ringFail go
$ fb MGV5-20538-ringFail pr
$ fb MGV5-20538-ringFail ok
```

### gitf release
- ```gif release [分支名] go```亦可直接输入```fr [分支名] go```：开始一个新的release。
- ```gif release [分支名] pr```亦可直接输入```fr [分支名] pr```：提交pull request到master和develop。
- ```gif release [分支名] ok```亦可直接输入```fr [分支名] ok```：合并release到master和develop，同时给master打tag，删除该release。
- 示例：
```
$ fr 6.0.0 go
$ fr 6.0.0 pr
$ fr 6.0.0 ok
```

### gitf hotfix
- ```gif hotfix [分支名] go```亦可直接输入```fh [分支名] go```：开始一个hotfix。
- ```gif hotfix [分支名] pr```亦可直接输入```fh [分支名] pr```：提交pull request到master。
- ```gif hotfix [分支名] ok```亦可直接输入```fh [分支名] ok```：合并到master和develop，同时删除该hotfix。
- 示例：
```
$ fh 6.0.1 go
$ fh 6.0.1 pr
$ fh 6.0.1 ok
```

## gitz命令集
Notes：gitz命令适用于需要多人开发feature，改bugfix或hotfix的情况，命令会自动解读之前操作的gitf命令，并创建对应的个人工作分支。
### gitz pull
- 命令格式 ```gitz pull [分支名]```亦可直接输入```zl [分支名]```
- 命令解释：从远程拉取对应分支代码到本地，
- 示例：
```
$ zl IOS-9-pageRefactor
```
- 上述zl命令会自动将远程feature-IOS-9-pageRefactor的代码，拉取到本地。

### gitz push
- 命令格式 ```gitz push [分支名]```亦可直接输入```zh [分支名]```
- 命令解释：完成个人分支（feature，bugfix或hotfix）的开发修改，提交pull request到父分支（feature，bugfix或hotfix）
- 示例：
```
$ zr
```

### gitz sub
- 命令格式：```gitz sub```亦可直接输入```zb```
- 命令解释：
  - 如果本地没有个人分支，则根据当前所在分支（gitf命令创建的分支类型：feature，bugfix，hotfix），以及本地配置的个人信息，自动创建并进入个人分支（feature，bugfix或hotfix）。如xxx-feature-IOS-9-pageRefactor。
  - 如果已有对应个人分支，则从父分支（feature，bugfix或hotfix）切换到子分支。
- 示例：
```
$ zb
```

### gitz super
- 命令格式：```gitz super```亦可直接输入```zp```
- 命令解释：从personal feature，personal bugfix或personal hotfix切换回其父分支。
```
$ zp
```

### gitz request
- 命令格式：```gitz request```亦可直接输入```zr```
- 命令解释：请求子分支代码合并、审核。（feature，bugfix或hotfix）
```
$ zr
```

### gitz remove
- 命令格式：```gitz remove [分支名]```亦可直接输入```zd [分支名]```
- 命令解释：删除当前用户自己的个人分支
```
$ zd
```


