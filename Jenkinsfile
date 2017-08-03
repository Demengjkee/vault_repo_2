@NonCPS
def match(regex, str) {
  def m = (str =~ regex)
  result = []
  def b = m.matches()
  println(b)
  if(b) {
    for(def i = 1; i <= m.groupCount(); i++) {
       result.add(m.group(i))
    }
  }
  return result
  /*
  sh """
  
    echo ${m.group(0)}
    echo ${m.group(1)}
  """
  */
}

node {
  checkout scm
  def res = sh(returnStdout: true, script:"git log -1 --pretty=%B")
  def r = match(/Merge pull request #(\d+) from (\w+)\/(\w+)/, res)
  println(r)
  
}
