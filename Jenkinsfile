pipeline {
  agent {
    dockerfile {
      filename 'Dockerfile'
    }

  }
  stages {
    stage('docker build') {
      steps {
        sh '''image_version=`date +%Y%m%d%H%M`;
echo $image_version;
#cd JucheapCore
git pull --rebase origin master;


docker build -t registry.cn-hongkong.aliyuncs.com/lxxsgy/aspnetcoretest:$image_version .;

docker login -u sgylxx -p sgylxx520 registry.cn-hongkong.aliyuncs.com

docker push registry.cn-hongkong.aliyuncs.com/lxxsgy/aspnetcoretest:$image_version;
'''
      }
    }
  }
}