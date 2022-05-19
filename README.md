# docker-promprog
Docker HW for PromProg X5 course

Запуск:
 - 1 часть: 
 cd task-docker/cmake-with-flask; 
 docker build -t cmake-flask . ;
docker run --rm -it -p 5000:5000 --name cmake-with-flask cmake-flask;