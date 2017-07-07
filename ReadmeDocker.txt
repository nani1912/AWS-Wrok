By Using these commands we can perform "Docker" Web Application launch:

1. sudo yum install -y docker ## Docker Installation
2. sudo service docker start  ## Stats Docker
3. sudo usermod -a -G docker ec2-user ## Adding ec2-user into docker group (We can perform docker commands without sudo)
4. docker info ## Verify that the ec2-user can run Docker commands without sudo. 
5. sudo yum install -y git ## Install git
6. git clone https://github.com/awslabs/ecs-demo-php-simple-app ## Clone the simple PHP application onto your system.
7. cd ecs-demo-php-simple-app ## Change directories to the ecs-demo-php-simple-app folder
8. cat Dockerfile ## A Dockerfile is a manifest that describes the base image to use for your Docker image and what you want installed and running on it.

        (This Dockerfile uses the Ubuntu 12.04 image. 
        The RUN instructions update the package caches, install some software packages for the web server and PHP support, 
        and then add your PHP application to the web server's document root. 
        The EXPOSE instruction exposes port 80 on the container, and the CMD instruction starts the web server.)
9. docker build -t aws_account_id.dkr.ecr.us-east-1.amazonaws.com/amazon-ecs-sample . 
        (Build the Docker image from your Dockerfile and tag it as amazon-ecs-sample in your default Amazon ECR registry. 
        Substitute aws_account_id with your AWS account ID.)
10. docker images ## (verify that the image was created correctly and that the image name contains a repository that you can push to (My AWS instance))        
11. docker run -p 80:80 aws_account_id.dkr.ecr.us-east-1.amazonaws.com/amazon-ecs-sample 
        (Run the newly built image. The -p 80:80 option maps the exposed port 80 on the container to port 80 on the host system.)
12. Finally use your public DNS (must allow port 80 (http)) on new web browser!! you can see the result of your Web Application.
