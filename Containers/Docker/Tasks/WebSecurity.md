First step: This will download the images to your linux machine by pulling it from docker hub. 
use the [docker images] command to view the downlaoded images 
docker pull bkimminich/juice-shop
docker pull vulnerables/web-dvwa



Second step: run the image (-d for deattached) (-p for port) followed by the image name
docker run -d -p 127.0.0.1:3000:3000 bkimminich/juice-shop:latest


Third step:
Open up the web browser, go to local host 127.0.0.1:3000 on port 3000.

NOTE: Port can be of your choice, in this example I have used 3000
