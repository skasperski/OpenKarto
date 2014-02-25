cmake_minimum_required (VERSION 2.6)
project (OpenKarto)

include_directories(source)

SET(KARTO_SOURCE_FILES
  source/Any.cpp
  source/Event.cpp
  source/Exception.cpp
  source/Geometry.cpp
  source/Grid.cpp
  source/GridIndexLookup.cpp
  source/Identifier.cpp
  source/Logger.cpp
  source/Meta.cpp
  source/MetaAttribute.cpp
  source/MetaClass.cpp
  source/MetaClassManager.cpp
  source/MetaEnum.cpp
  source/MetaEnumHelper.cpp
  source/MetaEnumManager.cpp
  source/Module.cpp
  source/Mutex.cpp
  source/Object.cpp
  source/Objects.cpp
  source/OccupancyGrid.cpp
  source/OpenKarto.cpp
  source/OpenMapper.cpp
  source/Parameter.cpp
  source/PoseTransform.cpp
  source/RangeTransform.cpp
  source/Referenced.cpp
  source/RigidBodyTransform.cpp
  source/Sensor.cpp
  source/SensorData.cpp
  source/SensorRegistry.cpp
  source/String.cpp
  source/StringHelper.cpp
)

SET(KARTO_INCLUDE_FILES
  source/OpenKarto/AbstractGpsEstimationManager.h
  source/OpenKarto/Event.h
  source/OpenKarto/Identifier.h
  source/OpenKarto/MetaAttribute.h
  source/OpenKarto/MetaEnumHelper.h
  source/OpenKarto/Mutex.h
  source/OpenKarto/OpenMapper.h
  source/OpenKarto/Referenced.h
  source/OpenKarto/SmartPointer.h
  source/OpenKarto/Any.h
  source/OpenKarto/Exception.h
  source/OpenKarto/List.h
  source/OpenKarto/MetaClass.h
  source/OpenKarto/MetaEnumManager.h
  source/OpenKarto/Object.h
  source/OpenKarto/Pair.h
  source/OpenKarto/RigidBodyTransform.h
  source/OpenKarto/String.h
  source/OpenKarto/CoordinateConverter.h
  source/OpenKarto/Geometry.h
  source/OpenKarto/Logger.h
  source/OpenKarto/MetaClassHelper.h
  source/OpenKarto/Meta.h
  source/OpenKarto/Objects.h
  source/OpenKarto/Parameter.h
  source/OpenKarto/SensorData.h
  source/OpenKarto/StringHelper.h
  source/OpenKarto/Grid.h
  source/OpenKarto/Macros.h
  source/OpenKarto/MetaClassManager.h
  source/OpenKarto/MetaType.h
  source/OpenKarto/OccupancyGrid.h
  source/OpenKarto/PoseTransform.h
  source/OpenKarto/Sensor.h
  source/OpenKarto/TypeCasts.h
  source/OpenKarto/Deprecated.h
  source/OpenKarto/GridIndexLookup.h
  source/OpenKarto/Math.h
  source/OpenKarto/MetaEnum.h
  source/OpenKarto/Module.h
  source/OpenKarto/OpenKarto.h
  source/OpenKarto/RangeTransform.h
  source/OpenKarto/SensorRegistry.h
  source/OpenKarto/Types.h
)

add_definitions(-DUSE_TBB)

add_library(${PROJECT_NAME} SHARED ${KARTO_SOURCE_FILES})
target_link_libraries(${PROJECT_NAME} tbb)

install(FILES ${KARTO_INCLUDE_FILES} DESTINATION include/${PROJECT_NAME})
install(TARGETS ${PROJECT_NAME} LIBRARY DESTINATION lib)
