# Script generated with Bloom
pkgdesc="ROS - Launch files and tools for 3D simulation of Care-O-bot in gazebo simulator."
url='http://ros.org/wiki/cob_gazebo'

pkgname='ros-kinetic-cob-gazebo'
pkgver='0.6.9_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-cob-supported-robots'
'ros-kinetic-roslaunch'
)

depends=('ros-kinetic-cob-bringup'
'ros-kinetic-cob-default-robot-config'
'ros-kinetic-cob-gazebo-ros-control'
'ros-kinetic-cob-hardware-config'
'ros-kinetic-cob-script-server'
'ros-kinetic-control-msgs'
'ros-kinetic-gazebo-plugins'
'ros-kinetic-gazebo-ros'
'ros-kinetic-gazebo-ros-control'
'ros-kinetic-roslaunch'
'ros-kinetic-rospy'
'ros-kinetic-rostest'
'ros-kinetic-trajectory-msgs'
)

conflicts=()
replaces=()

_dir=cob_gazebo
source=()
md5sums=()

prepare() {
    cp -R $startdir/cob_gazebo $srcdir/cob_gazebo
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

