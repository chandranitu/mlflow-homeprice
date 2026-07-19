#method 1
docker build -t jenkins-maven-docker .

docker run -d \
  --name jen-mvn \
  --user root \
  -p 8081:8080 \
  -p 50000:50000 \
  -v jenkins_home:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v /home/hadoop/workspace/mlflow-homePrice:/workspace/mlflow-homePrice \
  jenkins-maven-docker
 
#url
http://0.0.0.0:8081/

#method2

docker run -d \
  --name jen-mvn \
  --user root \
  -p 8081:8080 \
  -p 50000:50000 \
  -v jenkins_home:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v /home/hadoop/workspace/mlflow-homePrice:/workspace/mlflow-homePrice \
  jenkins/jenkins



  #jenkins container
apt-get update

apt-get install -y \
    build-essential \
    gcc \
    g++ \
    gfortran \
    python3-dev \
    pkg-config
    
apt install python3.12-venv

