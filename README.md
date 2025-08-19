# Y_Serein第1章作业

> 本文档记录移动机器人运动规划第一章作业，主要工作内容为编程环境的搭建与功能包测试。

## 仿真环境：

- 虚拟机软件:VMware17.5

- Ubuntu系统版本20.04(ROS noetic)

- 仿真软件Rviz

## 环境搭建：

- 下载与编译工程：

  > 创建ros工作空间目录与功能包目录：
  >
  > > ```bash
  > > mkdir -p ~/slam_ws/src
  > > # 将hw_1/src中的三个文件夹复制到/slam_ws/src路径下
  > > # 直接编译会存在一些或由于编译环境不同导致的的报错，需要修改一些配置
  > > gedit ~/slam_ws/src
  > > gedit ~/slam_ws/src/grid_path_searcher/src/demo_node.cpp
  > > # 检索world-> 将107行的/world修改为world->保存->关闭
  > > gedit ~/slam_ws/src/grid_path_searcher/CMakeLists.txt
  > > # 将第29行的C++11修改为C++14->保存->关闭
  > > ```
  >
  > 初始化工作空间：
  >
  > > ```bash
  > > cd ~/slam_ws/src
  > > catkin_init_workspace
  > > ```
  >
  > 编译工作空间：
  >
  > > ```bash
  > > cd ~/slam_ws/
  > > catkin_make
  > > ```
  >
  > 配置环境变量：
  >
  > > ```bash
  > > echo "source ~/slam_ws/devel/setup.bash" >> ~/.bashrc
  > > source ~/.bashrc
  > > ```

## 功能包测试：

> ```bash
> # 新建第一个终端(键入Ctrl+Alt+T)
> roscore
> # 新建第二个终端
> rviz
> # 选择配置文件:鼠标滑到屏幕左上方保持->File->Open Config->~/slam_ws/src/grid_path_searcher/launch/rviz_config/demo.rviz->选择`Close without Saving`->跳出配置文件
> # 新建第三个终端
> roslaunch grid_path_searcher demo.launch
> ```

## 运行结果：

> ![image-20250724115217357](Image_ys/image-20250724115217357.png)


## 建立git工具

> ```bash
> # 下载并安装 Git
> sudo apt-get install git
> 
> # 配置github
> git config --global user.name "Y-Serein"
> git config --global user.email "2034"
> 
> # 项目目录初始化:若未创建项目->git init SLAM
> git init
> 
> # 加入上行索引
> git add .
> 
> # 编写上行注释
> git commit -m "Mrmp_01"
> 
> # 连接Github仓库
> git remote add origin https://github.com/Y-Serein/Mrmp_ys.git
> 
> # 将本地文件推送到Github
> git push origin Mrmp-1.0.1
> 
> # 输入ID
> Y-Serein
> 
> # 输出密码(现在上传要输入秘钥，获取方式：github-> settings(右上角个人)-> Developer settings(左侧最下面)-> Personal access tokens（个人访问Tokens）->Generate new token（生成新Tokens）->设置名称，token过期日期，以及权限(个人可全选))
> ***********************
> 
> ```

## git项目管理

> ```bash
> # 查看分支
> git branch -a
> 
> # 切换分支
> git checkout branchName
> 
> # 创建新分支的同时切换到新的分支
> git checkout -b newBranch
