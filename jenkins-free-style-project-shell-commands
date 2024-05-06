#echo "----------------Job started----------------"
#echo "----------------Provided GitHub repository cloned----------------"
#echo "----------------View which user is executing these tasks on our node----------------"
#whoami
#date

#Steps to perform Prior to the below tasks
#sudo apt install docker.io
#sudo apt install docker-compose
#sudo usermod -aG docker jenkins
#sudo reboot

echo "----------------Cloning Code----------------"

echo "----------------Killing previous version of same container if it exists to avoid port is already allocated error----------------"
#if [[ docker ps -aq ]]
#docker stop $(docker ps -aq)

# Get a list of running containers
RUNNING_CONTAINERS=$(docker ps -aq)

# Check if any containers are running
if [ -z "$RUNNING_CONTAINERS" ]; then
    echo "No running containers found."
else
    # Loop through each container and stop/remove it
    for CONTAINER in $RUNNING_CONTAINERS; do
        echo "Killing and removing container: $CONTAINER"
        docker kill "$CONTAINER" &> /dev/null
        docker rm "$CONTAINER" &> /dev/null
    done
    echo "All running containers have been stopped and removed."
fi
echo "----------------Building Code----------------"
docker build . -t flask-mongo-app:1.0
echo "----------------Running Docker Container----------------"
docker run -d -p 5000:5000 -t flask-mongo-app:1.0
