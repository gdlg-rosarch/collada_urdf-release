# Script generated with Bloom
pkgdesc="ROS - This package contains a tool to convert Unified Robot Description Format (URDF) documents into COLLAborative Design Activity (COLLADA) documents. Implements robot-specific COLLADA extensions as defined by http://openrave.programmingvision.com/index.php/Started:COLLADA"
url='http://ros.org/wiki/collada_urdf'

pkgname='ros-lunar-collada-urdf'
pkgver='1.12.10_3'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('assimp'
'collada-dom'
'ros-lunar-angles'
'ros-lunar-catkin>=0.5.68'
'ros-lunar-cmake-modules'
'ros-lunar-collada-parser'
'ros-lunar-geometric-shapes'
'ros-lunar-resource-retriever'
'ros-lunar-roscpp'
'ros-lunar-tf'
'ros-lunar-urdf'
'urdfdom'
'urdfdom-headers'
)

depends=('assimp'
'collada-dom'
'ros-lunar-angles'
'ros-lunar-collada-parser'
'ros-lunar-geometric-shapes'
'ros-lunar-resource-retriever'
'ros-lunar-roscpp'
'ros-lunar-tf'
'ros-lunar-urdf'
'urdfdom'
'urdfdom-headers'
)

conflicts=()
replaces=()

_dir=collada_urdf
source=()
md5sums=()

prepare() {
    cp -R $startdir/collada_urdf $srcdir/collada_urdf
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

