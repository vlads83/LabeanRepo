#!/usr/bin/env groovy

import jenkins.model.Jenkins
import hudson.model.*
import groovy.json.*
import com.markwaite.Assert
import com.markwaite.Build
node('master'){
    //clean up work space
    step([$class: 'WsCleanup'])
    def this_result = checkout_result[implementation]
        print this_result
        def my_step = new com.markwaite.Build()
        def my_sha1 = my_step.getSHA1("HEAD")
        def my_check = new com.markwaite.Assert()
        my_check.assertCondition(first_checkout_result["GIT_COMMIT"] == this_result["GIT_COMMIT"], first_checkout_result["GIT_COMMIT"] + " != " + this_result["GIT_COMMIT"])
        my_check.assertCondition(first_checkout_result["GIT_COMMIT"] == my_sha1, first_checkout_result["GIT_COMMIT"] + " != " + my_sha1)
        my_check.assertCondition(first_checkout_result["GIT_COMMITTER_NAME"] == this_result["GIT_COMMITTER_NAME"], first_checkout_result["GIT_COMMITTER_NAME"] + " != " + this_result["GIT_COMMITTER_NAME"])
        my_check.assertCondition(first_checkout_result["GIT_COMMITTER_EMAIL"] == this_result["GIT_COMMITTER_EMAIL"], first_checkout_result["GIT_COMMITTER_EMAIL"] + " != " + this_result["GIT_COMMITTER_EMAIL"])
        my_check.assertCondition(first_checkout_result["GIT_AUTHOR_NAME"] == this_result["GIT_AUTHOR_NAME"], first_checkout_result["GIT_AUTHOR_NAME"] + " != " + this_result["GIT_AUTHOR_NAME"])
        my_check.assertCondition(first_checkout_result["GIT_AUTHOR_EMAIL"] == this_result["GIT_AUTHOR_EMAIL"], first_checkout_result["GIT_AUTHOR_EMAIL"] + " != " + this_result["GIT_AUTHOR_EMAIL"])
    env.GIT_REPO_URL = 'https://github.com/vlads83/LabeanRepo.git'
    echo "Detected Git Repo URL: ${env.GIT_REPO_URL} , branch : ${env.BRANCH_NAME} , committer : ${GIT_AUTHOR_EMAIL}"
      sh ("printenv")    
} 
      
