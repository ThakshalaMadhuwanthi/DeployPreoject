
pipeline{

agent any

triggers{
    githubPush()
}

stages{
    stage('gitclone'){
        steps{

           git branch: 'main',
           credentialsId: 'git',
           url: 'git@github.com:ThakshalaMadhuwanthi/DeployPreoject.git'
        }
    }
    stage('containercreate'){
        steps{
            sh 'docker compose up -d --build'
        }
    }

    stage('AnsibleDeploy'){
        steps{
            sh 'ansible-playbook -i Ansible/inventory Ansible/configure.yml'
        }
    }


}





}



