node {
  def vaultIp = "34.250.137.247"
  def vaultAddr = "http://${vaultIp}:8200"
  withCredentials([string(credentialsId: 'ROOT_TOKEN', variable: 'TOKEN')]) {
     sh """
       docker run -v ${WORKSPACE}:/mnt --rm --cap-add=IPC_LOCK -e "VAULT_ADDR=${vaultAddr}" vault /bin/sh -c "vault auth ${TOKEN};
       vault read secret/epam/password;
       vault read secret/sp5/password;"              
     """
  }
}
