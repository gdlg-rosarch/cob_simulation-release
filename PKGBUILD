# Script generated with Bloom
pkgdesc="ROS - This package provides some worlds for gazebo simulation."
url='http://ros.org/wiki/cob_gazebo_worlds'

pkgname='ros-kinetic-cob-gazebo-worlds'
pkgver='0.6.9_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-cob-default-env-config'
'ros-kinetic-roslaunch'
'ros-kinetic-rostest'
)

depends=('ros-kinetic-cob-default-env-config'
'ros-kinetic-controller-manager'
'ros-kinetic-gazebo-msgs'
'ros-kinetic-gazebo-ros'
'ros-kinetic-gazebo-ros-control'
'ros-kinetic-joint-state-controller'
'ros-kinetic-joint-state-publisher'
'ros-kinetic-position-controllers'
'ros-kinetic-robot-state-publisher'
'ros-kinetic-roslaunch'
'ros-kinetic-rospy'
'ros-kinetic-std-msgs'
'ros-kinetic-tf'
'ros-kinetic-velocity-controllers'
'ros-kinetic-xacro'
)

conflicts=()
replaces=()

_dir=cob_gazebo_worlds
source=()
md5sums=()

prepare() {
    cp -R $startdir/cob_gazebo_worlds $srcdir/cob_gazebo_worlds
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

