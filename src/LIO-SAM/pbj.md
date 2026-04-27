# 1.liosam_gnss数据记录
rosbag record -O lio_odom_only.bag \
  /clock \
  /tf /tf_static \
  /lio_sam/mapping/odometry \
  /lio_sam/mapping/odometry_incremental \
  /lio_sam/mapping/path \
  /odometry/imu \
  /odometry/imu_incremental \
  /odometry/gps \
  /odometry/navsat \

# 2.liosam数据记录
rosbag record -O lio_odom.bag \
  /clock \
  /tf /tf_static \
  /lio_sam/mapping/odometry \
  /lio_sam/mapping/odometry_incremental \
  /lio_sam/mapping/path \
  /odometry/imu \
  /odometry/imu_incremental \
  /odometry/gps \
  /odometry/navsat \

rosbag play 2025-04-18-13-30-35_mems_radyaw.bag KF_GINS_Navresult_trans.bag -r 1.0

# 2.liosam_dynamic数据记录-动态目标
rosbag record -O lio_odom_dynamic.bag \
  /clock \
  /tf /tf_static \
  /lio_sam/mapping/odometry \
  /lio_sam/mapping/odometry_incremental \
  /lio_sam/mapping/path \
  /odometry/imu \
  /odometry/imu_incremental \
  /odometry/gps \
  /odometry/navsat \

rosbag play car1_data.bag -r 3

# 4.liosam_dynamic_nognss数据记录-动态目标
rosbag record -O lio_odom_dynamic_nognss.bag \
  /clock \
  /tf /tf_static \
  /lio_sam/mapping/odometry \
  /lio_sam/mapping/odometry_incremental \
  /lio_sam/mapping/path \
  /odometry/imu \
  /odometry/imu_incremental \
  /odometry/gps \
  /odometry/navsat \

rosbag play car1_data.bag -r 3