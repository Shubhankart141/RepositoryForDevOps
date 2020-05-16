#!/usr/bin/env groovy
import hudson.model.*
import java.net.URL

node{
	
	stage('Git Checkout')
		{
		
			git 'https://github.com/edureka-git/DevOpsClassCodes.git'// code of the stage
		
		}
	
	stage('Compile'){
		
		withMaven(maven:'mymaven') {// code of the stage
		    
			sh 'mvn compile'
		    
			}
		
		}
	
	stage('Test'){
		
		try {
			
			withMaven(maven:'mymaven') 
			{// code of the stage
				
				sh 'mvn test'
				
				}
			
			}
		
		finally {
			
			junit 'target/surefire-reports/*.xml'
			
		}
		
	}
	
	stage('Package'){
		
		withMaven(maven:'mymaven') {// code of the stage
		    
			sh 'mvn package'
		
		}
		
	}

}
