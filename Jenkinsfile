#!groovy 

node {
   stage 'Checkout'
        checkout scm

   stage 'Setup'
        sh 'npm config set strict-ssl false'
        sh 'npm install'

   stage 'Mocha test'
        sh 'node --harmony ./node_modules/zombie/lib/index.js'
        sh './node_modules/mocha/bin/mocha'

   stage 'Cleanup'
        echo 'prune and cleanup'
        sh 'npm prune'
        sh 'rm node_modules -rf'
}
