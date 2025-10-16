# Y_Serein第3章作业

> 本文档为移动机器人运动规划课程第3章作业，主要工作内容为MATLAB环境下RRT算法的补全、ROS环境下RRT\*算法的补全。

## 仿真环境：

> 虚拟机软件：VMware17.5

> Ubuntu系统版本：20.04(ROS noetic)

> 仿真软件：MATLAB2025，Rviz等

## MatLab可视化结果截图：

> 扩展步长：10

> ![image-20250819101253240](Image_ys/image-20250819101253240.png) 

## RViz 可视化结果截图：

> ![image-20250821134823352](Image_ys/image-20250821134823352.png)



## 工作记录：

- 导入与配置工程：

  > ```bash
  > # 创建ros工作空间目录与功能包目录：
  > mkdir -p ~/slam_ws/src
  > 
  > # 将hw_1/src中的文件复制到/slam_ws/src路径下，直接编译会存在一些或由于编译环境不同导致的的报错，需要修改一些配置
  > gedit ~/slam_ws/src/map_gen/mockamap/src/ces_randommap.cpp
  > 
  > # 检索world-> 将42行的/world修改为world->保存->关闭
  > gedit ~/slam_ws/src/grid_path_searcher/CMakeLists.txt
  > 
  > # 将第以下文件中的C++11修改为C++14->保存->关闭
  > gedit ~/slam_ws/src/map_gen/map_generator/CMakeLists.txt
  > gedit ~/slam_ws/src/map_gen/mockamap/CMakeLists.txt
  > gedit ~/slam_ws/src/occ_grid/CMakeLists.txt
  > gedit ~/slam_ws/src/path_finder/CMakeLists.txt
  > gedit ~/slam_ws/src/rviz_plugins/CMakeLists.txt
  > gedit ~/slam_ws/src/self_msgs_and_srvs/CMakeLists.txt
  > ```
  >

- 初始化工作空间：

  > ```bash
  > cd ~/slam_ws/src
  > catkin_init_workspace
  > ```
  >

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
  > # 运行RRT算法:选择3D Nav Goal->选择两个坐标点->测试完成
  > ```
  
- 补全RTT\*算法的重连机制，具体细节见源文件。





## 思路指导

> ![image-20250821143759054](Image_ys/image-20250821143759054.png)

> ![image-20250821143819623](Image_ys/image-20250821143819623.png)

> ![image-20250821143838063](Image_ys/image-20250821143838063.png)

> ![image-20250821143859918](Image_ys/image-20250821143859918.png)
