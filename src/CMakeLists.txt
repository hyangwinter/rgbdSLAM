# 增加PCL库的依赖
FIND_PACKAGE( PCL REQUIRED COMPONENTS common io visualization filters)

# 增加opencv的依赖
FIND_PACKAGE( OpenCV 2.4 REQUIRED )
# 添加头文件和库文件
ADD_DEFINITIONS( ${PCL_DEFINITIONS} )
INCLUDE_DIRECTORIES( ${PCL_INCLUDE_DIRS}  )
LINK_LIBRARIES( ${PCL_LIBRARY_DIRS} )

ADD_LIBRARY( slambase slamBase.cpp )
TARGET_LINK_LIBRARIES( slambase ${OpenCV_LIBS} ${PCL_LIBRARIES} )

#ADD_EXECUTABLE( generate_pointcloud generatePointCloud.cpp )
#TARGET_LINK_LIBRARIES( generate_pointcloud ${OpenCV_LIBS} ${PCL_LIBRARIES} )

#ADD_EXECUTABLE( detectFeatures detectFeatures.cpp )
#TARGET_LINK_LIBRARIES( detectFeatures slambase ${OpenCV_LIBS} ${PCL_LIBRARIES} )

#ADD_EXECUTABLE( joinPointCloud joinPointCloud.cpp )
#TARGET_LINK_LIBRARIES( joinPointCloud slambase ${OpenCV_LIBS} ${PCL_LIBRARIES} )

ADD_EXECUTABLE( visualOdometry visualOdometry.cpp )
TARGET_LINK_LIBRARIES( visualOdometry slambase ${OpenCV_LIBS} ${PCL_LIBRARIES} )

