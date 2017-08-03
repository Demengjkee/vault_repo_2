@NonCPS
def match(regex, str) {
  def m = (str =~ regex)
  def result = []
  if(m.matches()) {
    for(def i = 0; i < m.groupCount(), i++) {
      result.add(m.group(i + 1)) 
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
  def r = match(/Merge pull request #(\d+) from (\w+)\/(\w+)/, res.readLines()[0])
  println(r)
  
}
