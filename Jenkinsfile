@NonCPS
def match(regex, str) {
  def m = str =~ regex
  prinln(m.matches())
  sh """
    echo ${m.group(0)}
    echo ${m.group(1)}
  """
}

node {
  checkout scm
  def res = sh(returnStdout: true, script:"git log -1 --pretty=%B")
  match(/Merge pull request #(\d+) from (\w+)\/(\w+)/,res.stripMargin())
  
}
