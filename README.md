# Docker-AzureFunctions
This repo describes how to create and deploy Azure Function apps to a docker container.

	
----------------
## Reference - Containers
### Deploying Basic Function To Container
This will create a basic function project and deploying it to a docker image. This does not cover creating the function itself.

Source: https://docs.microsoft.com/en-us/azure/azure-functions/functions-create-function-linux-custom-image?tabs=bash%2Cportal&pivots=programming-language-csharp

1. Create Function: ```func init <MyFunctionProj>```

2. Create Docker File: ```func init --docker-only```

3. Optional -- If using function key, create host_secrets.json.
    Add the following contents to DOCKERFILE
    ```
    ADD host_secret.json /azure-functions-host/Secrets/host.json
    ENV AzureWebJobsSecretStorageType=files
    ```

    -- Add functions --

4. Create Docker Image (Only Run This On Image Updates): ```docker build -f DockerFile -t <DockerImageName>:latest .```

5. Deploy Docker Image to Container: ```docker run -p 8080:80 <DockerImageName>```

### Removing Docker Container
Removes a docker container (must be stopped)
- ```docker container rm <container name or id>```
  

### Renaming Docker Container
Renames a docker container.
- ```docker container rename <container name> <container name new>```

	
----------------
## Reference - Images
### Removing Image
Get docker id by running ```docker images list```
- ```docker images rm <id>```
