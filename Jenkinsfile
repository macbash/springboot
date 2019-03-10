node {
    stage('Checkout') {
    checkout scm
}
stage('Deploy') {
sh "git clean -f && git reset --hard origin/master"
def pom = readMavenPom file: 'pom.xml'
//def version = pom.version.replace("-SNAPSHOT", ".${currentBuild.number}")
//println Version
println pom.version
}

}
