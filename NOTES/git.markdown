# Git 学习笔记

## 基础指令

### 用户名与邮箱

1.  读取

    ```bash
    git config --global user.name
    git config --global user.email
    ```

2.  写入

    ```bash
    git config --global user.name "sAkuraOfficial"
    git config --global user.email "mchaohao159@outlook.com"
    ```

### 查询日志

1.  基础指令

    ```bash
    git log
    ```

2.  可选参数
    `--all` 显示所有分支的记录
    `--graph` 以图形化显示
    `--pretty=oneline` 将记录显示为一行
    `--abbrev-commit` 优化 commit 标识符,使记录更为简短

3.  常用

    ```bash
    git log --pretty=oneline --all --graph --abbrev-commit
    ```

4.  版本切换后,只会显示直到当前版本的日志,此命令可以查看所有版本记录

    ```bash
    git --no-pager reflog
    ```

5.  进阶

    1.  将日志打印在终端上,而不是显示在分页程序里

        ```bash
        git --no-page log 参数
        ```

    2.  设置命令别名

        ```bash
        alias git-log='git log --pretty=oneline --all --graph --abbrev-commit'
        ```

        ![alt text](assets/image-3.png)

### 仓库操作

#### 以当前文件夹创建仓库,仓库创建成功文件夹会生产`.git`文件夹

```bash
git init
```
    
![alt text](assets/image.png)

#### 添加文件到暂存区

无论是新创建的文件,或是修改了的文件,都可以用该命令添加到暂存区
新创建的文件是`未跟踪`
修改了的文件是`未暂存`

1. 添加单个文件

    ```bash
    git add 文件路径
    ```

2. 使用此方法添加所有文件

    ```bash
    git add .
    ```

#### 将暂存区的文件提交到仓库

```bash
git commit
```

#### 查看状态

可以检测哪些文件被修改了/未被跟踪

```bash
git status
```

![alt text](assets/image-1.png)

#### 将暂存区中的文件提交到仓库

1. 在外部程序中编写更新消息

    ```bash
    git commit
    ```

2. 在命令中附带更新消息

    ```bash
    git commit -m "update a file"
    ```

    ![alt text](assets/image-2.png)

#### 切换版本

1. 文件内容不变,文件进入到暂存区中

    ```bash
    git reset 版本记录标识符
    ```

2. 强制切换版本,直接覆盖当前文件的内容

    ```bash
    git reset --hard 版本记录标识符
    ```

3. 回退后如何前进

    ```bash
    git --no-pager reflog
    ```
