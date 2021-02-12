node('master') {
    stage("Fetch Source Code") {
        cleanWS()
        git ([url:'https://github.com/harwanirahul/python-jenkins-pipeilne.git',branch:'add-functions-and-test])
    }
    
    
              dir("."){
                  printMessage('Running Pipeline')
       stage("Testing") {
           bat 'python test_functions.py'
        }
        stage("Deployment") {
            if (env.BRANCH_NAME == 'master') {
                printMessage('Deploying the master branch')
            } else {
                printMessage("No deployment for branch [${env.BRANCH_NAME}]")
            }
            
        }
        printMessage('Pipeline Complete')
    }
              }

def printMessage(message) {
    echo "${message}"
}
