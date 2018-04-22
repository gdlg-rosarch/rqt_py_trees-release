# Script generated with Bloom
pkgdesc="ROS - rqt_py_trees provides a GUI plugin for visualizing py_trees behaviour trees based on rqt_tf_tree."
url='http://ros.org/wiki/rqt_py_trees'

pkgname='ros-kinetic-rqt-py-trees'
pkgver='0.3.1_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('python2-mock'
'ros-kinetic-catkin'
'ros-kinetic-py-trees'
'ros-kinetic-py-trees-msgs'
'ros-kinetic-rqt-bag'
)

depends=('python2-pygraphviz'
'python2-rospkg'
'python2-termcolor'
'ros-kinetic-geometry-msgs'
'ros-kinetic-py-trees'
'ros-kinetic-py-trees-msgs'
'ros-kinetic-qt-dotgraph'
'ros-kinetic-rospy'
'ros-kinetic-rqt-bag'
'ros-kinetic-rqt-graph'
'ros-kinetic-rqt-gui'
'ros-kinetic-rqt-gui-py'
'ros-kinetic-unique-id'
)

conflicts=()
replaces=()

_dir=rqt_py_trees
source=()
md5sums=()

prepare() {
    cp -R $startdir/rqt_py_trees $srcdir/rqt_py_trees
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

