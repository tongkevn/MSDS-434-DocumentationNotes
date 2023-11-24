# Module 7: Microservice-based Machine Learning Model Implementation

Purpose: construct a demonstration of the construction of a containerized microservice application using Golang or Python on GCP or AWS.


# Amazon Web Services (AWS) Notes
[Click Here to Access AWS Recording](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=49322f92-665b-4776-8f7b-b0af01293880)

- Launch t2.micro instance that accepts all incoming traffic
- Run the following commands

```
mkdir golangMicro
cd golangMicro
mkdir data
vi main.go # reference main.go in repo

# install golang
sudo apt-get update
sudo apt install golang-go

# run go mod commands

go mod init github.com/HelloWorld/goProductAPI
go mod tidy

# install gorilla mux
sudo apt install golang-github-gorilla-mux-dev

# change to data directory
cd data

vi data.json # reference data.json file in repo

go back to golangMicro directory ("..")


# run go file
go run main.go


```

- check port to see if json data was deployed publicIPv4 DNS : <9090>

## Postman (for running curl commands)
- Launch Postman
- Copy paste publicIPv4DNS : <9090>
- Copy paste new data
- Use POST command to send data
