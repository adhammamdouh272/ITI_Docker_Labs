# Part 1:

## Creating a Registry:

![[part1_1.png]]

## Editing `daemon.json` file to make the registry insecure:

![[part1_2.png]]

![[part1_3.png]]

## Dockerfile for the custom Nginx image:

![[part1_4.png]]

## Building the Image:

![[part1_5.png]]

## Pushing the image to the private registry:

![[part1_6.png]]

## Testing the image from the private registry:

We first delete this image and then pull it again from the private registry and run container from it.
![[part1_7.png]]

![[part1_8.png]]![[part1_9.png]]

---
# Part 2:

## Docker Compose file:

![[Screenshots/Lab3/part2_1.png]]

## Running the compose file:

![[Screenshots/Lab3/part2_2.png]]

## Testing WordPress:

![[Screenshots/Lab3/part2_3.png]]

## Testing MySQL:

![[Screenshots/Lab3/part2_4.png]]

---
# Part 3:

## Modify flask app image:
we do this to make the flask app launch in Gunicorn server that will be used to connect to Nginx.

![[part3_9.png]]

## Re-tagging the flask app image and push it to registry:
![[part3_4.png]]
![[part3_5.png]]
![[part3_6.png]]
## Docker Compose file:

![[part3_1.png]]

## Running `Docker compose up` :

![[part3_3.png]]


> [!NOTE] Note
> We can now check if the website works by running `curl localhost:5000` inside the `flask_app` container or `curl localhost:8080` on Docker host and we will see tiger webpage.

## Configuring Nginx to connect to Gunicorn server:

We need to do 3 things:
1. Delete the `/etc/nginx/conf.d/defaul.conf` otherwise when we connect to nginx we will see the default nginx webpage not the flask app.
2. Add `/etc/nginx/conf.d/flask.conf` file that allows us to connect to the flask app and for that we use `Docker cp` command to copy `flask.conf` from docker host into the container.
3. reload nginx configuration.

![[part3_7.png]]

## Test the flask app:

![[part3_8.png]]

> [!NOTE] Note
> We can also use `curl localhost` on Docker host or inside `nginx_proxy` container to verify that the app is working as well.
