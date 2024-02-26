properties([parameters([string(defaultValue: 'james', description: '', name: 'YourName', trim: true)])])

stage 'Compile'
node() {
    checkout scm
    // use for non multibranch: git 'https://github.com/amuniz/maven-helloworld.git'
    def mvnHome = tool 'mvn-3.6.0'
    try {
        sh "${mvnHome}/bin/mvn clean test"
    }catch(e) {
        echo "exception"
    }
    stash 'working-copy'
}
