Purpose of this project is enabling step by step guide to learn docker with simple sample codes to enable learning for the beginers up to advanced level.

simple dotnet web api is being used for this tutorial.Visual studio is the code editor using

Steps to create dotnet web api

Open vscode terminal and run following command to create new project

dotnet new webapi -n weatherapp

use following command to run the created project

cd weatherapp
dotnet run

To access the app, click on the localhost url given in the terminal
ex: http://localhost:5171

Access the api using swagger
http://localhost:5171/swagger/index.html

Run project as docker

Add docker file with visual studio
Enable swagger run in both developer and prod mode in program.cs file
csproj should have Docker target os value
get more information, change appsettings.json
"Microsoft.AspNetCore": "Information"
get more information dev mode, change appsettings.Development
"Microsoft.AspNetCore": "Information"

launchSettings.json
Change useSSL: false

Build docker file
C:\Pushpa\GitHubRepo\DockerLearn> docker build --progress plain -t myapp:v1 -f weatherapp\Dockerfile .

Run docker
C:\Pushpa\GitHubRepo\DockerLearn> docker run -p 8080:80 --name weatherapp myapp:v1

--
linux musl - extra info
