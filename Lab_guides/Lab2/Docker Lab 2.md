Name: Adham Mamdouh El-Sherbini
# Part 1:

## Cloning app repo:

![[Screenshots/Lab2/1.png]]

## Modify requirements file of the application:

That is because this app uses very old version of flask which is not compatible with modern python versions and pip will produce an error if the you use the requirement file unmodified

![[Screenshots/Lab2/2.png]]
## Creating Dockerfile:

![[3.png]]

## Building Docker Image:

![[Screenshots/Lab2/4.png]]
## Running a Docker container from the Docker Image:

![[5.png]]

## Verify that the app works:

![[Screenshots/Lab2/6.png]]

## Login in Docker hub from CLI:

![[Screenshots/Lab2/7.png]]

## Re-tagging the image and push it to Docker Hub:

![[Screenshots/Lab2/8.png]]
## Verify that the Image is uploaded successfully:

![[Screenshots/Lab2/9.png]]

## Testing the image after upload:

I have deleted the image from the host so that i can pull it again from Docker hub and run a container from it.

![[10.png]]

---
# Part 2:

## Creating Network:

![[Screenshots/Lab2/part2_1.png]]

## Creating Volume:

![[Screenshots/Lab2/part2_2.png]]

## Running the container:

![[Screenshots/Lab2/part2_3.png]]

## Getting inside the container and creating the web page:

![[Screenshots/Lab2/part2_4.png]]

![[part2_5.png]]
## Editing Nginx config file:

This allows us to change the port of the website to 8080 and change the root directory to `/var/www/html` .

![[part2_6.png]]
![[part2_7.png]]

## Check the website from the docker host:

![[part2_8.png]]
## Check the website from physical host:

![[part2_9.png]]
![[part2_10.png]]
