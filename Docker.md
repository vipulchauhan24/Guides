# Commands to create an Image

## Command to create image without arguments

- `sudo docker build -t <image_name>:<tag_name> .`

## Command to create image with arguments

- `sudo docker build -t <image_name>:<tag_name> --build-arg <arg_name>=<arg_value> .`


# Command to run docker image

- `sudo docker run --name <container_name> -p 80:80 <image_name>:<tag_name>`

# Command to push image to docker hub

- `sudo docker tag <imageid> <dockerid>/<repositoryname>:<tag_name>`

- `sudo docker login`
enter password
enter username

- `sudo docker push <dockerid>/<repositoryname>:<tag_name>`

# Command to pull image from docker hub

- `sudo docker pull <dockerid>/<repositoryname>:<tag_name>`

# Step to remove sudo requirement
- Run `sudo groupadd docker`.
- Run `sudo usermod -aG docker $USER`.
- Run `newgrp docker`. for changes to take effect
- Run `docker run hello-world` to test changes.