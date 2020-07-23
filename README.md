# JAVAC
## Initial setup (only needs to be done once)
1. cd to your git folder for this repo
2. pip install --target ./package ask_sdk_core
3. pip install --target ./package ask_sdk_model
4. cd package
5. zip -r9 ${OLDPWD}/function.zip .    [do not miss the dot at the end]
6. cd ..
7. zip -g function.zip lambda_function.py 3choices.json
8. nano ~/.aws/credentials
9. replace the [default] credentials to    
aws_access_key_id=AKIASVQFDLYILAVIRE6F   
aws_secret_access_key=ILhkNjEICqCRb2RO4kQFkp4Dr8vzWIj5nM93YvOH

## Steps to update lambda function to Alexa
1. cd to your git folder for this repo
2. If you have made changes to 3choices.json, run zip -g function.zip 3choices.json
3. If you have made changes to lambda.function, run zip -g function.zip lambda_function.py
4. aws lambda update-function-code --function-name AlexaHackathonJavacLambdaFunction --zip-file fileb://function.zip
