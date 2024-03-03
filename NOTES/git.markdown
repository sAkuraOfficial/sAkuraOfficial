# Git 学习笔记

## 基础指令

### 用户名与邮箱

-   读取

    ```bash
    git config --global user.name
    git config --global user.email
    ```

-   写入

    ```bash
    git config --global user.name "sAkuraOfficial"
    git config --global user.email "mchaohao159@outlook.com"
    ```

### 日志

-   查询日志

    -   基础指令
        ```bash
        git log
        ```
    -   可选参数
        `--all` 显示所有分支的记录
        `--graph` 以图形化显示
        `--pretty=oneline` 将记录显示为一行
        `--abbrev-commit` 使输出的记录更为简短

    ```bash
    git log --pretty=oneline --all --graph --abbrev-commit
    ```

-   设置命令别名

    ```bash
    alias git-log='git log --pretty=oneline --all --graph --abbrev-commit'
    ```

### 仓库

-   创建仓库

    -   以当前文件夹创建仓库,仓库创建成功文件夹会生产`.git`文件夹

    ```bash
    git init
    ```

    ![alt text](assets/image.png)

-   添加文件到暂存区

    -   无论是新创建的文件,或是修改了的文件,都可以用该命令添加到暂存区
    -   新创建的文件是`未跟踪`
    -   修改了的文件是`未暂存`

    -   添加单个文件

        ```bash
        git add 文件路径
        ```

    -   使用此方法添加所有文件
        ```bash
        git add .
        ```

-   将暂存区的文件提交到仓库

    ```bash
    git commit
    ```

-   查看状态

    -   可以检测哪些文件被修改了/未被跟踪

    ```bash
    git status
    ```

    ![alt text](assets/image-1.png)

-   将暂存区中的文件提交到仓库

    -   在外部程序中编写更新消息
        ```bash
        git commit
        ```
    -   在命令中附带更新消息
        ```bash
        git commit -m "update a file"
        ```

    ![alt text](assets/image-2.png)
