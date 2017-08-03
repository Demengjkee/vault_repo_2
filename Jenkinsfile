node {
  checkout scm
  res = sh(returnStdout: true, script:"git log -1 --pretty=%B")
  println(res.stripMargin())
}
