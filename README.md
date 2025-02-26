# Docker
Prepare docker file for microservice deploy

dotnet new webapi -o MyMicroservice --no-https
cd MyMicroservice
dotnet run

fsutil file createnew Dockerfile 0
fsutil file createnew .dockerignore 0
docker build -t mymicroservice .
docker images
docker run -it --rm -p 3000:8080 --name mymicroservicecontainer mymicroservice
docker ps
