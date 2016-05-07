stage "Build"
node {
  bat: python build.py
}

stage "Unit test"
node {
  bat: python unittest.py
}

stage "Coverage & System test"

parallel {
  node {
    bat: python coverage.py
  }
  node {
    bat: python systemtest.py
  }
}
