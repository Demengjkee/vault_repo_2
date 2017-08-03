@NonCPS
def match(regex, str) {
  def m = str =~ regex
  sh """
    echo ${m.group(0)}
  """
}

node {
  checkout scm
  def res = sh(returnStdout: true, script:"git log -1 --pretty=%B")
  match(/Merge pull request #(\d+) from (\w+)\/(\w+).*/,res.stripMargin())
  
}
