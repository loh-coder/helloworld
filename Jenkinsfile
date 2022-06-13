#!groovy 

node {
   stage 'Checkout'
        checkout scm

   stage 'Setup'
        sh 'npm config set strict-ssl false'
        sh 'npm cache clean -f'
        sh 'npm install -g n'
        sh 'n stable'

   stage 'Mocha test'
        sh './node_modules/mocha/bin/mocha'

   stage 'Cleanup'
        echo 'prune and cleanup'
        sh 'npm prune'
        sh 'rm node_modules -rf'
}
