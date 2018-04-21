# Script generated with Bloom
pkgdesc="ROS - The cob_simulation stack includes packages to work with Care-O-bot within simulation environments, e.g. gazebo."
url='http://ros.org/wiki/cob_simulation'

pkgname='ros-kinetic-cob-simulation'
pkgver='0.6.9_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-cob-bringup-sim'
'ros-kinetic-cob-gazebo'
'ros-kinetic-cob-gazebo-objects'
'ros-kinetic-cob-gazebo-worlds'
)

conflicts=()
replaces=()

_dir=cob_simulation
source=()
md5sums=()

prepare() {
    cp -R $startdir/cob_simulation $srcdir/cob_simulation
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

