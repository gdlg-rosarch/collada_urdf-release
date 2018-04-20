# Script generated with Bloom
pkgdesc="ROS - This package contains a C++ parser for the Collada robot description format. The parser reads a Collada XML robot description, and creates a C++ URDF model. Although it is possible to directly use this parser when working with Collada robot descriptions, the preferred user API is found in the urdf package."
url='http://ros.org/wiki/collada_parser'

pkgname='ros-lunar-collada-parser'
pkgver='1.12.10_3'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('collada-dom'
'ros-lunar-catkin'
'ros-lunar-class-loader'
'ros-lunar-roscpp'
'ros-lunar-urdf'
'ros-lunar-urdf-parser-plugin'
'urdfdom-headers'
)

depends=('collada-dom'
'ros-lunar-class-loader'
'ros-lunar-roscpp'
'ros-lunar-urdf-parser-plugin'
'urdfdom-headers'
)

conflicts=()
replaces=()

_dir=collada_parser
source=()
md5sums=()

prepare() {
    cp -R $startdir/collada_parser $srcdir/collada_parser
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
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

