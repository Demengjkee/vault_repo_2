@NonCPS
node {
  checkout scm
  def res = sh(returnStdout: true, script:"git log -1 --pretty=%B")
  def m = res.stripMargin() =~ /Merge pull request #(\d+) from (\w+)\/(\w+).*/
  if(m) {
    def a =res.stripMargin()
    def b = m.group(0)
    def c = m.group(1)
    sh """
      echo ${a}
      echo ${b}
      echo ${c}
    """
  }
}
