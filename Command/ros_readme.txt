

                                                                                            ROS 常用指令         
                                                                                                                      创建：2015.10.22




(1)source /opt/ros/hydro/setup.bash        执行 vim .bashrc 添加source ...

(2)创建ros工作空间 ：  mkdir -p ~/catkin_ws/src
                      cd ~/catkin_ws/
                      catkin_make
                      source devel/setup.bash  （也可以将  source /home/gongwenbo/catkin_ws/devel/setup.bash 添加到 .bashrc 文件 ）

(3)创建ros程序包 :  cd ~/catkin_ws/src
                   catkin_create_pkg beginner_tutorials std_msgs rospy roscpp 

(4)roscore 无法初始化，网络配置问题 ： sudo chown -R <your_username> ~/.ros

(5)节点： rosnode list ； rosnode info +节点名 ；

(6)话题： rostopic echo +话题名 ；rostopic list -v ； rostopic type [topic] ；rostopic pub [topic] [msg_type] [args] ；rostopic hz [topic] ； 

(7) 服务：rosservice list；rosservice call 调用带参数的服务；rosservice type 输出服务类型；rosservice find 依据类型寻找服务；

(8) 编辑文件：rosed [package_name] [filename]；

(9)消息：创建消息 cd ~/catkin_ws/src/beginner_tutorials
                       mkdir msg
                       echo "int64 num" > msg/Num.msg
                       package.xml 里添加：  <build_depend>message_generation</build_depend>
                                             <run_depend>message_runtime</run_depend>

                       catkin_package(
                                      ...
                                      CATKIN_DEPENDS message_runtime ...
                                      ...)
                             
                       add_message_files(
                                      FILES
                                      Message1.msg
                                      )

                      find_package(catkin REQUIRED COMPONENTS roscpp rospy std_msgs message_generation)

                      generate_messages()

                       rosmsg show [message type]
                       rosmsg list	List all messages
                       rosmsg packages	List packages that contain messages
           
(10)录制与发布话题： rostopic list -v  查看话题
                    mkdir ~/bagfiles  创建录制包
                    cd ~/bagfiles
                    rosbag record -a  录制所有话题

                    rosbag info <your bagfile> 查看录制话题
                    rosbag play <your bagfile> 播放话题
(11)roslaunch 应用：
(12)ros在多PC使用： 1.需要一个master，即在一个PC运行 roscore 
                   2.所有节点都必须通过配置 ROS_MASTER_URI 连接到同一个master IP 。
                   3.任意两台机器间任意两端口都必须要有完整的、双向连接的网络。
                   4.每台机器都必须向其他机器广播其能够解析的名字。
                   5.(有一个特例——驱动节点必须运行在跟硬件设备有物理连接的机器上）
    配置步骤： ssh yourname(hal)@hal IP ； roscore
               
              ssh hal(hal is your pc name)
              export ROS_MASTER_URI=http://hal:11311    (可以添加 .bashrc 文件里)
              rosrun rospy_tutorials listener.py
  
              ssh marvin
              export ROS_MASTER_URI=http://hal:11311
              rosrun rospy_tutorials talker.py
              

(13) 不需要节点，直接向话题发消息 ：rostopic pub [topic] [msg_type] [args]
                                  rostopic pub -1 /turtle1/command_velocity turtlesim/Velocity  -- 2.0  1.8  (2.0 and 1.8 are parameter at topic )
                                    

(14)sudo apt-get install ros-indigo-rqt ros-indigo-rqt-common-plugins ros-indigo-rqt-robot-plugins
  //rqt安装


()()()()()()()()()()
































