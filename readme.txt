Github & circleci credentials : 
victoriliescu77@gmail.com
testare22

Case 1 - PRODSUP-001
1. I have created a new repository named (renamed) PRODSUP-001 and I imported there Case1 path https://github.com/mtedone/podam  (email notification about finishing this import received from GitHub). Project was automatically imported in Circleci. A new public key was added to project. My public GitHub path is : https://github.com/viliescu/PRODSUP-001.git
2. In Circleci everything is green except revision 3fa99dc form gh-pages Branch - Status is No Tests (also receive email notification about this from Circleci)
After reading circleci documentation - https://circleci.com/docs/manually - I realise that I have to add a circle.yml file manually and put there the path where errprs will pe uploaded
Test:  
post:
    - mkdir -p $CIRCLE_TEST_REPORTS/junit/
    - find . -type f -regex ".*/target/surefire-reports/.*xml" -exec cp {} $CIRCLE_TEST_REPORTS/junit/ \;
3. Then I rebuild and everything was fine (even tried a 2 containers in parallel)

mail received : 
Success! Success	
build report	viliescu/PRODSUP-001 #30
branch	gh-pages
commits	Create circle.yml f2cdd35 
author	viliescu
Yay, all your tests have passed!
Your commands (they all ran successfully):
Starting the build
Start container
Enable SSH
Restore source cache
Checkout using deploy key: 35:26:86:4a:6c:3d:0b:bd:76:ff:02:83:10:12:69:53
Configure the build
Restore cache
Save cache
mkdir -p $CIRCLE_TEST_REPORTS/junit/
find . -type f -regex ".*/target/surefire-reports/.*xml" -exec cp {} $CIRCLE_TEST_REPORTS/junit/ \;
Collect test metadata
Collect artifacts
Disable SSH
