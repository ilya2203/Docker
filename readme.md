# Docker homework
There are 2 folders with dockerfile and folder with index.html
Starting with docker run for registry

    docker run -d -p 5000:5000 --restart=always --name registry registry:2
  
Than create two images and push it to local registry

    docker build -t nginx1 -t localhost:5000/nginx1_v1 .
    sudo docker push localhost:5000/nginx1_v1

    docker build -t nginx2 -t localhost:5000/nginx2_v1 .
    sudo docker push localhost:5000/nginx2_v1

Last step is run docker-compose.yaml

    docker-compose up -d
