pipeline {
		agent {
				label {
							label "built-in"
							customWorkspace "/mnt/projects"
				
				}
		}
		
		environment {
						
						url = "https://github.com/mohanwaje/game-of-life.git"
		
		}
		
		stages {
		
				stage ("ClONE_PROJECT"){
								
							steps {
										sh "rm -rf *"
										sh "git clone $url"
							
							}
				
				}
				
				stage ("BUILD_PROJECT") {
							
								steps {
											
											sh "cd game-of-life && mvn clean install -DskipTests=true"
								
								}
				
				}
				
				stage ("COPY") {
							
							steps {
										sh "rm -rf /mnt/projects/*"
										sh "cp -r game-of-life/gameoflife-web/target/gameoflife.war /mnt/projects"
							
							}
				
				
				}
		
		
		
		}

}
