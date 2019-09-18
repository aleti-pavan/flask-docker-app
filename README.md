# flask-docker-app

Tutorial for Dockerizing a simple flask app

1. make sure you have docker installed, this is tested on `19.03.2 version`

2. Here is the folder structure
      ```
      flask-docker-app/
      ├── Dockerfile
      ├── README.md
      ├── app.py
      └── requirements.txt
      ```
3. Build the image with `docker build -t flask-docker-app .`

    Above command builds the docker app and can be checked using `docker images` command

4. Run the container with created image using `docker run -d -p 5000:5000 flask-docker-app`

5. Check the running container with `docker ps`

6. Test with `curl http://localhost:5000` or pur the url into the browser

  ```
  curl http://localhost:5000
  {
      "This is Flask App": "app"
  }

  ```


# Let's push it to dockerhub

1. `docker login` (Enter Username/Password)

2. Tag it with `docker tag flash-docker-app aletipavan/flask_app`

3. Push it with `docker push aletipavan/flask_app`


# Let's prune the images/containers

1. `docker kill <containerID>` (kill the running container)

2. `docker system prune -a`   say `y` (clears all images and containers)

3. Pull the image from dockerhub and Run `docker run -d -p 5000:5000 aletipavan/flask_app`
