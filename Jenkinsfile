node {
  checkout scm
  def res = sh(returnStdout: true, script:"git log -1 --pretty=%B")
  if(m = res.stripMargin() =~ /Merge pull request #(\d+) from (\w+)\/(\w+).*/) {
    println(res.stripMargin())
    println(m.group(0))
    println(m.group(1))
  }
}
