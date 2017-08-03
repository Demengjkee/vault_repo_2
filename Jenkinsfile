@NonCPS
def match(regex, str) {
  def m = (str =~ regex)
  def result = []
  if(m.matches()) {
    for(def i = 0; i < m.groupCount(); i++) {
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
  def info = match(/Merge pull request #(\d+) from (\w+)\/([\w\/]+)/, res.readLines()[0])
  if(info.size() == 3) {
    stage("PROD Deploy") {
      
    }
    
    stage("Set tag") {
      def release_tag = "${info[2]}/release/${info[0]}"
      sh """
        git tag --force ${release_tag} `git log -1 --pretty=format:%h`
        git push --force --tags 
      """
      /*https://${token}@github.com/${repo}.git*/
    }
    
    stage("wiki gen") {
      
    }
  }
  
}
