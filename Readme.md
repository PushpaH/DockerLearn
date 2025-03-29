# Docker Sample Guide

### The Repository contains a sample dotnet project with a Docker file for containerized deployments.This guide provides instrcution on setting up,builing and running the project using Docker.Purpose of this project is enabling step by step guide to learn docker with simple sample codes to enable learning for the beginers up to advanced level.

* ### Code : simple dotnet web api is being used for this tutorial.
* ### IDE : Visual studio is the code editor

## Steps to create dotnet web api

1. Open vscode terminal and run following command to create new project

        dotnet new webapi -n weatherapp

2. Use following command to run the created project

        cd weatherapp
        dotnet run

3. To access the app, click on the localhost url given in the terminal
ex: http://localhost:5171

4. Access the api using swagger
http://localhost:5171/swagger/index.html

## Run project as docker

1. Add docker file with visual studio
2. Enable swagger run in both developer and prod mode in program.cs file
3. Add Docker target os value to csproj 
4. Change appsettings.json to get more information
    * "Microsoft.AspNetCore": "Information"
5. To get more information on dev mode, change appsettings.Development
    * "Microsoft.AspNetCore": "Information"

6. Change launchSettings.json
    * Change useSSL as false

7. Build docker file using below command
    * docker build --progress plain -t myapp:v1 -f weatherapp\Dockerfile .

8. Run docker using below command
* docker run -p 8080:80 --name weatherapp myapp:v1


