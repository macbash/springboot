node {
    stage('Checkout') {
    checkout scm
}
stage('Deploy') {
sh "git clean -f && git reset --hard origin/master"
def pom = readMavenPom file: 'pom.xml'
def version = pom.version.replace("-SNAPSHOT", ".${currentBuild.number}")
println version
println pom.version

if(env.BRANCH_NAME == 'master'){
 sh "mvn deploy scm:tag -Drevision=$BUILD_NUMBER-RELEASE"
} else {
 sh "mvn deploy -Drevision=$BUILD_NUMBER-SNAPSHOT"
}

}

}
