# Create-a-CI-CD-Pipeline-Build-and-Deploy-.Net-WebApp-on-Azure-Devops

## Prerequisites

Create an organization, project and push local repo to azure repos

![image](https://user-images.githubusercontent.com/96833570/216345131-2585fc36-8c97-42a9-b652-f831baf3784c.png)

## Building `.net webapp` locally

```
dotnet restore HelloWorldApp.Web.csproj
dotnet build HelloWorldApp.Web.csproj --configuration Release
```

### Testing the binaries

`dotnet HelloWorldApp.Web.dll`

![image](https://user-images.githubusercontent.com/96833570/216345954-fbf7a1f9-c0e5-4f43-83e1-510d94089bda.png)


![image](https://user-images.githubusercontent.com/96833570/216347462-a79edc66-d4a3-404b-b9b1-de5481cd4fa1.png)


![image](https://user-images.githubusercontent.com/96833570/216347779-7b54a7df-4df8-49e6-97e7-7a43b944df45.png)


`dotnet publish HelloWorldApp.Web.csproj --configuration Release --output ./output`

![image](https://user-images.githubusercontent.com/96833570/216349300-ad071a72-f37b-4af2-9646-a233e2c19d59.png)

Here is our artifact.



Since i got `##[error]No hosted parallelism has been purchased or granted` error i setup my self-hosted agent. If you have parallel jobs, you can skip this step. 

### Running your self-hosted agent

https://www.bmc.com/blogs/azure-devops-build-release-agents/

You can follow the steps here.


## Creating a pipeline on azure devops

![image](https://user-images.githubusercontent.com/96833570/216350101-61482c18-d2f8-479b-9129-be6758cb2b94.png)


![image](https://user-images.githubusercontent.com/96833570/216353230-7d1413bb-3c8b-4112-b13c-b785100ca1cf.png)


![image](https://user-images.githubusercontent.com/96833570/216353102-0d86cd6a-f1b6-43e9-8446-b14296d362b5.png)


`--configuration $(BuildConfiguration) --output $(Build.ArtifactStagingDirectory)`

![image](https://user-images.githubusercontent.com/96833570/216354253-667412e8-2dd5-4b98-98c2-87555ef4b177.png)


![image](https://user-images.githubusercontent.com/96833570/216354588-517f96ac-861b-4f7a-8058-3ef9dc0abfce.png)


## Make sure your agent is online and save&queue 

![image](https://user-images.githubusercontent.com/96833570/216365137-d9906c12-5a7b-4f03-acb4-e3021b8ffb38.png)


![image](https://user-images.githubusercontent.com/96833570/216424971-ca914f93-25a7-4d6a-9211-f4f396ebf2e3.png)

![image](https://user-images.githubusercontent.com/96833570/216425935-e2d1256b-eee5-4c8b-8283-e17c5f20f643.png)

## Validation Step 1 

![image](https://user-images.githubusercontent.com/96833570/216427734-6cd111a7-ebbc-4113-bff9-f3e4062121bc.png)

![image](https://user-images.githubusercontent.com/96833570/216427813-796ac20a-41c5-49a2-85fe-9ccf1d96928e.png)

![image](https://user-images.githubusercontent.com/96833570/216428006-feaf936a-5aa3-4b8a-ac7b-ada58c28fd98.png)

![image](https://user-images.githubusercontent.com/96833570/216428058-cdded9e2-f1ea-4e67-957d-c07fcffb8437.png)


