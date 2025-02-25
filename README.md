# Docker Static Web Hosting 🚀  

This project demonstrates how to host a static website inside a Docker container using Nginx.  

## Steps to Deploy  

### Step 1: Create a Project Directory  
  
    mkdir my-static-site  
    cd my-static-site

### Step 2: Create DockerFile
 
  #### Use the latest Nginx image  
        FROM nginx:latest  

  #### Copy the contents of the current directory into the Nginx web root  
       COPY . /usr/share/nginx/html  

  #### Expose port 80 for web traffic  
       EXPOSE 80  

 #### Run Nginx in the foreground  
       CMD ["nginx", "-g", "daemon off;"]

##### FROM nginx:latest → Uses the latest official Nginx image.
##### COPY . /usr/share/nginx/html → Copies your static files into the container's web root.
##### EXPOSE 80 → Informs Docker that the container will listen on port 80.
##### CMD ["nginx", "-g", "daemon off;"] → Runs Nginx in the foreground to keep the container running.

### Step 3: Add static website files
  Move your HTML, CSS, and JavaScript files into the my-static-site directory.
### Step 4: Build the Docker Image
    docker build -t my-web-host .
##### Loads the Dockerfile and metadata.
##### Transfers necessary files into the Docker image.
##### Saves the built image with a unique SHA256 hash and tags it as "my-web-host"

### Step 5: Run the Docker Container
      docker run -d -p 8080:80 --name my-container my-web-host
##### Runs the container in detached mode (-d).
##### Maps port 8080 on the host to port 80 in the container.
##### Names the container "my-container".

### Step 6: Access the Website
    Open a browser and visit:
                     http://localhost:8080




     
