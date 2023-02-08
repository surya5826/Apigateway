node {
stage("Git Clone"){

git branch: 'main', url: 'https://github.com/surya5826/Apigateway.git'
}

stage("Docker build"){
 sh 'mvn clean package'
 sh 'docker build -t apigateway:latest .'
sh 'docker images'
stage("Deploy"){
 sh 'docker rm -f apigateway||true'
//  sh 'docker rm -f apigateway||true' 
sh ' docker run -d -p 9999:9999 --name apigateway apigateway:latest'
}
}
}
