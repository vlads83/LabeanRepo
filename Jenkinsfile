#!/usr/bin/env groovy

import jenkins.model.Jenkins
import hudson.model.*
import groovy.json.*
node('master'){
    //clean up work space
    step([$class: 'WsCleanup'])
    env.GIT_REPO_URL = 'https://github.com/vlads83/LabeanRepo.git'
     sh ("printenv")    
} 
      
