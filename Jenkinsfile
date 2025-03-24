pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    sh '''
                        # Load nvm if not already loaded
                        export NVM_DIR="/home/hunter/.nvm"
                        [ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"  # This loads nvm

                        # Ensure the correct Node.js version is used
                        nvm use 23.4.0
                        
                        # Add npm's path to the PATH environment variable
                        export PATH=$PATH:/home/hunter/.nvm/versions/node/v23.4.0/bin
                        
                        # Use npm to install dependencies
                        /home/hunter/.nvm/versions/node/v23.4.0/bin/npm install
                    '''
                }
            }
        }
    }
}
