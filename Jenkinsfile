node {
  checkout scm
  def res = sh(returnStdout: true, script:"git log -1 --pretty=%B")
  def m = res.stripMargin() =~ /Merge pull request #(\d+)from (\w+)/
  println(m.group(0))
  println(m.group(1))
  println(res.stripMargin())
}
