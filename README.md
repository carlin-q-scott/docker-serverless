# docker-serverless

A simple container for running serverless commands

## How to Use

### Windows

1. Open the Windows Powershell.
2. Navigate to your source directory containing your serverless.yml configuration file.
3. Run this command, adding what serverless command you want to run on the end:

With AWS CLI installed localled:

```ps
docker run -it --rm -v $env:USERPROFILE/.aws:/root/.aws -v $pwd/:/src carlin/serverless sls
```

Without AWS CLI:

```ps
docker run -it --rm -e AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY -v $pwd/:/src carlin/serverless sls
```

You can generate the two KEYs used in the command above from the AWS Console website. They're called API Keys and are found in your user profile in IAM.

### Linux

1. Open the Linux terminal.
2. Navigate to your source directory containing your serverless.yml configuration file.
3. Run this command, adding what serverless command you want to run on the end:

```sh
docker run -it --rm -v $HOME/.aws:/root/.aws -v $(pwd):/src carlin/serverless sls
```

Without AWS CLI:

```sh
docker run -it --rm -e AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY -v $(pwd):/src carlin/serverless sls
```

You can generate the two KEYs used in the command above from the AWS Console website. They're called API Keys and are found in your user profile in IAM.
