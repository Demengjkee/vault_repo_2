node {
  result = sh (script: "git log -1 | grep '\\[ci skip\\]'", returnStatus: true) 
  println(result)  
}
