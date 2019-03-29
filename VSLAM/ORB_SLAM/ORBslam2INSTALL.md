#
mkdir  -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
#
cd catkin_ws／src
git clone https://github.com/bosch-ros-pkg/usb_cam usb_cam
cd usb_cam
mkdir build 
cd build 
cmake ..
make

#
sudo apt-get install libglew-dev  
sudo apt-get install cmake  
sudo apt-get install libboost-dev libboost-thread-dev libboost-filesystem-dev
#
git clone https://github.com/stevenlovegrove/Pangolin.git  
cd Pangolin  
mkdir build  
cd build  
cmake -DCPP11_NO_BOOST=1 ..  
make -j
#
sudo apt-get install libeigen3-dev
#
cd catkin_ws／src
git clone https://github.com/raulmur/ORB_SLAM2.git ORB_SLAM2
#
sudo apt-get install libqt4-dev qt4-qmake libqglviewer-dev libsuitesparse-dev libcxsparse3.1.4
sudo apt-get install libcholmod
#
cd catkin_ws/src/ORB_SLAM2/Thirdparty/g2o/
mkdir build
cd build
cmake ..
make
#
cd catkin_ws/src/ORB_SLAM2/Thirdparty/DBoW2
mkdir build
cd build
cmake ..
make
#
cd catkin_ws/src/ORB_SLAM2
mkdir build 
cd build 
cmake ..
make
#
goto "catkin_ws/src/ORB_SLAM2/Examples/ROS/ORB_SLAM2/src"
open "ros_mono.cc"
change the topic of sub into "usb_cam/image_raw"
#
cd catkin_ws/src/ORB_SLAM2/Examples/ROS/ORB_SLAM2/
mkdir build
cd build
cmake ..
make

#end, but you may meet some error when build the stereo and rgbd, you can choose to do not build them. You can just run the Mono camera demo.



