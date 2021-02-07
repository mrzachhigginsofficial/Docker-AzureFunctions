# Docker-AzureFunctions
This repo describes how to create and deploy Azure Function apps to a docker container.


## Reference
### Deploying Basic Function To Container
This will create a basic function project and deploying it to a docker image. This does not cover creating the function itself.
Source: https://docs.microsoft.com/en-us/azure/azure-functions/functions-create-function-linux-custom-image?tabs=bash%2Cportal&pivots=programming-language-csharp

1.) Create Function: ```func init <MyFunctionProj>```

-- Add functions --

2.) Create Docker File: ```func init --docker-only```

3.) Create Docker Image: ```docker build -f DockerFile -t sandboxfunctions:latest .```

4.) Run Docker Image: ```docker run -p 8080:80 sandboxfunctions```
