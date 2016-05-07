stage "Build"
node {
  checkout scm
  bat: 'python build.py'
}

stage "Unit test"
node {
  bat: 'python unittest.py'
}

stage "Coverage & System test"

parallel (
  coverage: {
    node {
      bat: 'python coverage.py'
    }},
  systemtest: {
    node {
      bat: 'python systemtest.py'
    }}
)
