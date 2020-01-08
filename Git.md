#  Git和Github的基本使用

### 一、GitHub基本概念

* **仓库（Repository）**：用来存放项目代码，每个项目对应一个仓库，多个开源项目对应多个仓库

* **收藏（Star）**:收藏项目方便下次查看

* **复制克隆项目（Fork）**：复制克隆项目到自己库（两个独立存在）类似于保存到自己网盘（会显示forked from ***）

* **事务卡片（Issue）**：向库主人发起讨论，探讨项目，提出问题或者想法

* **发起请求（Pull Requst）**：比如李四Fork了张三的库，然后李四添加了一个文件，然后向张三发起请求，张三觉得不错的话，将添加的文件合并到张三自己的库里面

  ![img](https://github.com/1306588647/Technology-Sharing/blob/master/Picture/clip_image001.png)

* **关注（Watch）**：如果关注了某个项目，如果该项目由任何更新，则在自己的主页就可以通知

* **Github主页**：登录账号显示的页面

* **仓库主页**：主要显示项目的信息，如：项目代码、版本、收藏、关注fork情况等

* **个人主页**：自己的信息

----

### 二、Git的基本本地操作

#### 1、目的

* 通过Git管理Github托管项目代码


#### 2、Git工作区域

* **Working Directory（工作区）**：添加、编辑、修改文件等动作
* **暂存区**：暂存已修改的文件最后统一提交到Git仓库中

* **Git Repository（Git仓库）**：最终确定的文件保存到仓库，成为一个新的版本，并且对他人可见

#### 3、向仓库中添加文件流程

* 查看当前状况

  ```
  git status
  ```

* 从工作区提交到暂存区

  ```
  git add 文件名.后缀名
  git add -A .    			来一次添加所有改变的文件
  git add -A					表示添加所有内容
  git add . 					表示添加新文件和编辑过的文件不包括删除的文件
  git add -u 					表示添加编辑或者删除的文件，不包括新添加的文件
  ```

* 从暂存区提交到仓库

  ```
  git commit -m "提交描述"
  ```

  ![git提交流程](C:\Users\13065\Desktop\图片\git提交流程.png)



#### 2、Git初始化及本地仓库创建和操作

* 设置或者覆盖用户名

  ```
  git config --global user.name "输入你的Github用户名"
  ```

* 设置用户名邮箱

  ```
  git config --global user.email "输入你的邮箱"
  ```

  ***注意：该设置在Github仓库主页显示谁提交了该文件***
  
* 查看初始化信息

  ```
  git config --list			查看所有
  git config user.name		查看用户名
  git config user.email		查看邮箱
  ```

* 删除信息

  ```
  git config --global --unset user.name "yourName"
  git config --global --unset user.email "your@email.com"
  ```

* 初始化仓库

  ```
  git init
  ```

* 创建文件

  ```
  touch 文件名.后缀名    如：touch Demo.txt
  ```

* 修改文件

  * 先修改同在git目录下的文件

    ```
    vi 文件名.后缀名              也可以直接手动去修改文件
    ```

  * 重新添加到缓存区

  * 重新提交到仓库

* 删除文件

  * 删除同在git下的文件（可有可无，也可以直接进行第二步）

    ```
    rm 文件名.后缀名          也可以直接手动去删除文件
    ```

  * 删除暂存区的文件

    ```
    git rm -cached 文件名.后缀名
    ```

  * 删除暂存区和工作区的文件

    ```
    git rm 文件名.后缀名
    ```

  * 最后一步还要提交到仓库

----

### 三、Git管理远程仓库

* 先将已存在远程仓库的文件下载到同一Git目录下

  ```
  git clone 仓库地址
  ```

* 或者先初始化一个库然后直接连接远程仓库下载文件

  ```
  git remote add origin 			仓库地址
  git pull origin master			下载文件
  ```

* 将工作区文件提交到暂存区

* 将暂存区文件提交到仓库

* 将仓库文件提交到远程仓库

  ```
  git push
  ```

  

----

### 四、搭建个人站点

#### 1、访问站点

* https://用户名.github.io

#### 2、搭建步骤

1. 创建个人站点  ->  新建仓库**（注：仓库名必须是[用户名.github.io]）**

2. 创建一个html文件即可

   **注意：**

   * Github Pages仅支持静态网页
   * 仓库里只能是html文件

3. 然后再setting打开自动生成即可

