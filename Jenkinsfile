node('master') {
    stage("Fetch Source Code") {
        git([url: 'https://github.com/seanyan68/lesson5', branch: 'add-functions-and-tests'])
    }
    
    dir('.') {
        printMessage('Running Pipeline')
        stage("Testing") {
            sh 'ls -al'
            sh 'echo pipeline mutil'
            sh 'python test_functions.py'
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
