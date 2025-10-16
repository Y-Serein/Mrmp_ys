# Y_Serein第4章作业

> 本文档为移动机器人运动规划课程第4章作业，主要工作内容为ROS环境下最优轨迹规划算法的补全。

## 测试环境：

> 虚拟机版本：VMware17.5

> Ubuntu系统版本：20.04(ROS noetic)

> 测试软件：Rviz

## RViz 可视化结果截图：

> ![image-20251016143522878](Image_ys/image-20251016143522878.png) 

> ![028710f4-8781-41c8-8d6f-bab6c65bcbd5](Image_ys/028710f4-8781-41c8-8d6f-bab6c65bcbd5.png) 



## 工作记录：

- 导入与配置工程：

  > ```bash
  > # 创建ros工作空间目录与功能包目录：
  > mkdir -p ~/slam_ws/src
  > 
  > # 将hw_1/src中的文件复制到/slam_ws/src路径下，直接编译会存在一些或由于编译环境不同导致的的报错，需要修改一些配置
  > gedit ~/slam_ws/src/grid_path_searcher/src/demo_node.cpp
  > # 检索world-> 将107行的/world修改为world->保存->关闭
  > 
  > gedit ~/slam_ws/src/grid_path_searcher/CMakeLists.txt
  > # 将第29行的C++11修改为C++14->保存->关闭
  > ```
  >

- 初始化工作空间：

  > ```bash
  > cd ~/slam_ws/src
  > catkin_init_workspace
  > ```
  >

- 完成代码编写

  > ```bash
  > # 具体修改参考源文件
  > vim ~/slam_ws/src/grid_path_searcher/src/demo_node.cpp
  > vim ~/slam_ws/src/grid_path_searcher/src/hw_tool.cpp
  > vim ~/slam_ws/src/grid_path_searcher/include/hw_tool.h
  > ```

- 编译工作空间：

  > ```bash
  > cd ~/slam_ws/
  > catkin_make
  > ```
  >

- 配置环境变量：

  > ```bash
  > echo "source ~/slam_ws/devel/setup.bash" >> ~/.bashrc
  > source ~/.bashrc
  > ```

- 功能包测试

  > ```bash
  > # 新建第一个终端(键入Ctrl+Alt+T)
  > roscore
  > 
  > # 新建第二个终端
  > roslaunch path_finder rviz.launch
  > 
  > # 运行RRT算法:选择3D Nav Goal->选择一个坐标点->测试完成
  > ```


