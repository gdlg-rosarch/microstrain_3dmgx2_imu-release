# Script generated with Bloom
pkgdesc="ROS - A driver for IMUs compatible the microstrain 3DM-GX2 and 3DM-GX3 protocol. Includes a heavily modified standalone driver pulled from the player distribution, and a ROS node."
url='http://www.ros.org/wiki/microstrain_3dmgx2_imu'

pkgname='ros-kinetic-microstrain-3dmgx2-imu'
pkgver='1.5.12_2'
pkgrel=1
arch=('any')
license=('LGPL'
)

makedepends=('log4cxx'
'ros-kinetic-catkin'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-message-generation'
'ros-kinetic-roscpp'
'ros-kinetic-self-test'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-tf'
)

depends=('log4cxx'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-message-runtime'
'ros-kinetic-roscpp'
'ros-kinetic-self-test'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=microstrain_3dmgx2_imu
source=()
md5sums=()

prepare() {
    cp -R $startdir/microstrain_3dmgx2_imu $srcdir/microstrain_3dmgx2_imu
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

