## **Problem: Challenges in Software Development**

Traditional software development faces issues with consistency, portability, and dependency management across different environments. Developers often encounter "it works on my machine" problems, leading to deployment delays and compatibility issues.

<div style="text-align:center">
    <img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1709829824587/bf7b5c6a-a654-4250-948c-ac1e810eb4b7.webp" alt="Docker Image">
</div>

## **Introducing Docker**

Docker provides a solution by packaging applications into lightweight, portable containers. These containers encapsulate everything needed to run the software, ensuring consistency and eliminating environment discrepancies.

### **What is Docker?**

Docker is a platform for developing, shipping, and running applications in containers.

> Let’s imagine you would like to build a website or a web application. What do you need to make your next Facebook, YouTube, or Twitter up and running?

> For sure you will need to develop some code, as it is a key part of every or web software. But the code on its own is not enough. Websites and applications consist of many additional parts, like databases, configuration files, runtime libraries, and other third-party software.

**Docker** is a tool that allows you to take all the parts and bundle them together into one package, called **the container**.

<div style="text-align:center">
    <img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1708623272129/423b386c-efe8-458b-992a-8d3b20a92c9e.png" alt="Docker Image">
</div>


### **Container :**

> The container is a standardized unit that can be created on the fly to deploy a particular application or environment It could be an Ubuntu container, CentOS container, etc. to full-fill the requirement from an operating system point of view

A container is a lightweight, standalone, and executable package that includes everything needed to run a piece of software, including the code, runtime, libraries, and system tools.

Containers provide a consistent and reproducible environment across different systems.

> Containerization is increasingly popular because containers are:

* Flexible: Even the most complex applications can be containerized.
    
* Lightweight: Containers leverage and share the host kernel, making them much more efficient in terms of system resources than virtual machines.
    
* Portable: You can build locally, deploy to the cloud, and run anywhere.
    
* Loosely coupled: Containers are highly self sufficient and encapsulated, allowing you to replace or upgrade one without disrupting others.
    
* Scalable: You can increase and automatically distribute container replicas across a datacenter.
    
* Secure: Containers apply aggressive constraints and isolations to processes without any configuration required on the part of the user
    

### **Docker Architecture:**

> Understanding Docker's architecture is essential for mastering Docker. At its core, Docker consists of three main components:

* Docker Engine: The runtime environment for containers, responsible for building, running, and managing containers.
    
* Docker Client: The command-line interface (CLI) used to interact with the Docker Engine, allowing users to create, manage, and monitor containers.
    

Docker Registry: A centralized repository for Docker images, where users can store and share images with others.

### Docker Images

> A Docker image is a lightweight, standalone, and executable package that contains everything needed to run an application, including the code, runtime environment, libraries, and system tools.

### Dockerfile

> **Dockerfile:** Docker can build images automatically by reading the instructions from a `Dockerfile`. A `Dockerfile` is a text document that contains all the commands a user could call on the command line to assemble an image.


<div style="text-align:center">
    <img src="https://media.licdn.com/dms/image/D4E22AQFTuPoNomSg0Q/feedshare-shrink_1280/0/1697956207832?e=1712793600&v=beta&t=bx0liV2x--56BXNJB2k_vTlBepYggY3V_zgwwW10UBQ">
</div>


# **  
Docker Core Concepts:**

* **Docker Image:** A read-only template that contains a set of instructions for creating a Docker container. Images are used to create containers.
    
* **Docker Container:** A runnable instance of a Docker image that runs in isolation on the host machine.
    
* **Dockerfile:** A text file that contains instructions for building a Docker image.
    
* **Docker Registry:** A repository for storing and sharing Docker images.
    
* **Docker Network:** A feature that allows containers to communicate with each other and with the host machine. Docker provides several network drivers for different use cases, including bridge, overlay, and macvlan.
    
* **Docker Compose:** A tool for defining and running multi-container Docker applications. Docker Compose uses a YAML file to configure the services that make up the application.
    

## **Most commonly used tags in a Dockerfile:**

* `FROM`: Specifies the base image to use for the image being built.
    
* `RUN`: Executes a command during the build process.
    
* `CMD`: Specifies the default command to run when the container is started.
    
* `ENV`: Sets an environment variable in the container.
    
* `COPY`: This copies files or directories from the host machine only into the container.
    
* `ADD` : Add is similar to copy with addition it allows A URL instead of a local file/directory & extracts tar from the source directory into the destination.
    
* `EXPOSE`: Exposes a specific port or ports to be used by the container.
    
* `LABEL`: Adds metadata to the image in the form of key-value pairs.
    
* `USER`: Specifies the user to use when running the container.
    
* `WORKDIR`: As the name says, it sets the working directory for the container.
    

## **Most used Commands**

> If you know these 4 commands well, you know 80% of Docker 😅
> 
> 1️⃣ `docker build` to build an Image for your application  
> 2️⃣ `docker push` to publish your image to a Registry  
> 3️⃣ `docker pull` to download your image from a registry to a server or local workstation  
> 4️⃣ `docker run` the holy grail that spins up an actual container from an image and runs your application.

## Let's Create the *"Hello World" of Docker using NodeJS*

### Create a Dockerfile:

> Create **a** file named `Dockerfile` (without any file extension) and add the following content:

```dockerfile
# Use the official lightweight Node.js image
FROM node:alpine

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Run `node app.js` when the container launches
CMD ["node", "app.js"]
```

### Create a Node.js Application:

> Create a file named `app.js` in the same directory as your Dockerfile and add the following content:

```javascript
console.log("Hello, World!");
```

### Build the Docker Image:

> Open a terminal or command prompt, navigate to the directory containing your Dockerfile and Node.js application file, and run the following command to build the Docker image:

```bash
docker build -t hello-world .
```

### Run the Docker Container:

> Once the Docker image is built, you can run a container based on that image. Run the following command:

```bash
docker run hello-world
```

You should see the output `Hello, World!` printed to the console, indicating that your Node.js application is running successfully inside the Docker container.

> That's it! You've created a simple "Hello World" example using Docker. You can modify the Node.js application code or Dockerfile as needed and rebuild the Docker image to reflect any changes.

If you found this helpful, don't forget to give it a thumbs-up and hit the follow button! 🌟

Let's keep the learning journey going! 🚀📚

With ❤️ by - Hrushikesh Makode  
For more such blogs, check out:  
➡️ [blogs.hrushikesh.tech](https://blogs.hrushikesh.tech)  
➡️ [hrushikesh.tech](https://hrushikesh.tech)