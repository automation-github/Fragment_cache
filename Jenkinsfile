pipeline {
  agent any
  stages {
    stage('fragment_cache_rb') {
      steps {
        build 'test_fragment_cache_rb_5.1'
      }
    }
    stage('fragment_cacherbinfo') {
      steps {
        build 'test_fragment_cache_fragmentinfo_5.1'
      }
    }
    stage('copy results') {
      steps {
        sh 'scp -p root@$target_cluster:/tmp/Fragment_cache/*.xml .'
      }
    }
  }
  environment {
    target_cluster = '10.65.173.162'
  }
}