# docker-serverless
A simple container for running serverless commands

# How to Use

Regardless of your OS (Linux, Windows), start by setting up environment variables for your Cloud Environment. I provide examples for AWS below but other environments will be similar. 

You can also optionally supply the environment variables in the command at step #3 by appending `=your_key` to the end of each -e argument.

## Windows
1. Open the Windows command prompt; don't use Powershell.
2. Navigate to your source directory containing your serverless.yml configuration file.
3. Run this command, adding what serverless command you want to run on the end:  
   `docker run -it --rm -v %CD%:/src -w /src -e AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY carlin/serverless sls`

## Linux
1. Open the Linux terminal.
2. Navigate to your source directory containing your serverless.yml configuration file.
3. Run this command, adding what serverless command you want to run on the end: 
   `docker run -it --rm -v $(pwd):/src -w /src -e AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY carlin/serverless sls`