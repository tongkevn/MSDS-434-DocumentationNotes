# Module 8: Asynchronous Microservice Application Development

Purpose: construct a demonstration of the construction of a containerized (pub/sub) microservice application using Golang or Python on AWS or GCP.


# Amazon Web Services (AWS) Notes
[Please Click Here to Access AWS Recording](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=a3324706-b62f-4b97-a02e-b0b601137380)

- Launch a t2.micro instance in AWS
- run the following shell commands


```

# install docker
sudo apt update
sudo snap install docker

# install rabbitmq (docker)
sudo docker pull rabbitmq
sudo docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3.11-management


```

- check if rabbitmq was deployed by going accessing publicIPv4DNS:<15672>
- username / password: guest / guest
- once rabbitmq is live, we can start putting in commands for rabbitmq to monitor
- in a new terminal:

```
# install golang
sudo apt install golang-go

# input producer go file
vi prod.go # (copy paste rabbitMQ_producer.go file, make sure to update the file to the appropriate publicIPv4 DNS)


# install ampq

go install github.com/streadway/amqp@latest
go mod init github.com/TutorialEdite/go-rabbitmq-tutorial
go mod tidy

# run prod.go (run this 3-4 times)
go run prod.go
```


- check if traffic is being displayed in rabbitmq

- create a rabbitmq consumer file to see the messages in the producer file


```
vi cons.go # (copy/paste consumer.go file, make sure to update the file to the appropriate publicIPv4DNS)

go run cons.go
```
