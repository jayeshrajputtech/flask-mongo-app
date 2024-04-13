# Demonstartion of Docker Networking usign 2 Tier Web Application
## Application utilizes Flask and Mongodb that has 3 routes defined
1) "/" :- This is a home route that displays {"message":"Welcome to Tasks app!"} 
2) "/tasks/" :- This route displays the tasks that is stored inside the mongodb
3) "/task/" :- This route is used to create tasks.

The main aim of this project is to learn establish communication between two containers without using docker-compose and demonstrate the docker networking.

The first task was t create an Docker network of type custom bridge using "docker network create flask-mongo-app-network" command
![image](https://github.com/jayeshrajputtech/flask-mongo-app/assets/166933906/37f14075-4e3c-432f-8d10-714c9824e040)

Then next task was to create an Dockerfile to containerize the application. Then build the image and run the container of flask application inside the custome bridge network "flask-mongo-app-network".
![image](https://github.com/jayeshrajputtech/flask-mongo-app/assets/166933906/1887ee81-9bb7-4fda-83f5-fa32c905cf0c)

Once the flask application container is up and running next task was to run the mongodb container inside the flask-mongo-app-network" so that both container can comunicate with each other using their respective names.
![image](https://github.com/jayeshrajputtech/flask-mongo-app/assets/166933906/02f9ab1b-1d62-44bb-8536-b472444ad188) 

Postman is used to test the application endpoints
1) "/" 
![image](https://github.com/jayeshrajputtech/flask-mongo-app/assets/166933906/c8552896-7c56-41ee-8f18-267593a707ac)
2) "/task"
![image](https://github.com/jayeshrajputtech/flask-mongo-app/assets/166933906/7f596026-16f9-4f8f-8a08-102afa08de17)
3) "/tasks/"
![image](https://github.com/jayeshrajputtech/flask-mongo-app/assets/166933906/4d7ce823-24ad-43d7-be26-0b9bde8f5335)

Web Interface
![image](https://github.com/jayeshrajputtech/flask-mongo-app/assets/166933906/b55a0d5f-bd76-43e6-86ee-865a0b56036a)

![image](https://github.com/jayeshrajputtech/flask-mongo-app/assets/166933906/39cbe236-52ad-48fc-ae1e-a4609704356f)

This project demonstrated how to create a custom bridge network and run containers inside that to isolate them from the default bridge docker network.
