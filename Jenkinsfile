pipeline{
    agent{
        label "srividya1"
    }
    stages{
        stage("vcs"){
            steps{
                git url:"https://github.com/DevProjectsForDevOps/StudentCoursesRestAPI.git" ,
                    branch:"master"
                 
            }
        }
        stage("image build"){
            steps{
               sh 'docker image build -t studentcourserestapi:1.0 .'
               sh 'docker tag studentcourserestapi:1.0 siri1418/studentcourserestapi:1.0'
            }        
        }
        stage("docker hub push"){
            steps{
               sh 'docker push siri1418/studentcourserestapi:1.0'

            }
        }
        stage("start container"){
            steps{
                sh 'docker container run -d -p 8083:8080 --name "stdcourse" studentcourserestapi:1.0'
            }
        }
    }
}