node {
   stage ('checkout repository') {
      deleteDir()
      checkout scm
   }

   stage ('Render configurations') {
     sh 'ansible-playbook generate_configurations.yaml'
   }

   stage ('Unit Testing') {
     //Do some kind of "linting" on code to make sure nothing is screwed up
   }


   stage ('Deploy Configurations to Dev') {
     sh 'python3 -m venv jenkins_build'
     sh 'jenkins_build/bin/python -m pip install -r requirements.txt'
     sh 'git clone https://github.com/carlniger/napalm-ansible'
     sh 'cp -r napalm-ansible/napalm_ansible/ jenkins_build/lib/python3.6/site-packages/'
     sh 'jenkins_build/bin/python napalm-ansible/setup.py install'
     sh '''sed -i -e 's/\\usr\\/local/jenkins_build/g' ansible.cfg'''
     sh 'ansible-playbook deploy_configurations.yaml -e "ansible_python_interpreter=jenkins_build/bin/python"'
   }


   stage ('Functional Integration Testing') {
     // ping stuff to check dev
   }


   stage ('Promote Configurations to Production') {
     // ping stuff to check dev
   }

   stage ('Production Functional/Integration Testing') {
    // ping stuff to check prod
   }


}
