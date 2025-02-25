# docker-static-web-hosting

step 1:
  # mkdir my-static-site
  # cd my-static-site

step 2:
  create Dockerfile
     2.1   FROM nginx:latest
        This line specifies the base image for your Docker container.
     2.2    COPY . /usr/share/nginx/html
        This line copies the conents of your current directory into the /usr/share/nginx/html directory insixe the container
     2.3     EXPOSE 80
        This line tells container will listen to port 80
     2.4     CMD ["nginx","-g","daemon off;"]
         This line tells that the command will be executed whem container starts
         It run the nginx web server in the foreground preventing  it from running as daemon (background)

step 3:
        move the html,css,js files in the current directory (my-static-site)

step 4:
  # docker build -t my-web-host .
        Loads Dockerfile,Metadata
        Transfers necessary files from your project into docker image
        copies your local files into /usr/file/nginx/html
        saves the build image with a unique SHA256 hash tags "my-web-host"

step 5:
  # docker run -d -p 8080:80 --name my-container my-web-host
        Runs the container on port 80 in detached mode

step 6:
  Access the browser 
        http://localhost:8080
        
     
