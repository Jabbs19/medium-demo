pipeline {
  
agent { docker { image 'ruby:2.6.3' } }
  
stages {
    
stage('requirements') {
      
steps {
        
sh 'gem install bundler -v 2.0.2'
      }
    }
    
stage('build') {
      
steps {
        
sh 'bundle install'
      }
    }
    
stage('test') {
      
steps {
        
sh 'rake ci:all'
      }
      
post {
        
always {
          
junit 'test/reports/TEST-AppTest.xml'
        }
      }    
    }
  }
}
