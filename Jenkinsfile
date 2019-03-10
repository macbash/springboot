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
 sh "mvn -DreleaseVersion=${version} -DdevelopmentVersion=${pom.version} -DpushChanges=false -DlocalCheckout=true -DpreparationGoals=initialize release:prepare release:perform -B"
}

}
