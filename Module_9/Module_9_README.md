# Module 9: Application and System Monitoring

Purpose: construct a demonstration of the Prometheus and Grafana applications

# Amazon Web Services (AWS) Notes
[Click Here to Access AWS Recording](https://northwestern.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=1214d8aa-c57f-486c-a707-b0bc002eae7e)

- Launch a t2.micro instance that allows all incoming traffic
- Run the following shell commands

## Prometheus

```
sudo apt update
sudo snap install docker

# install prometheus and deploy to port 9090

sudo apt update
sudo snap install docker
sudo docker pull prom/prometheus
sudo docker network create network
sudo docker volume create prometheus-data

vi prometheus.yml (copy / paste prometheus.yml in repository)

sudo docker container run --name prometheus -v prometheus.yml -v prometheus-data:/prometheus -p 9090:9090  prom/prometheus

```

- check if prometheus is running by accessing "PublicIPv4DNS":9090

## Grafana

- start a new terminal
- run the following shell commands

```
sudo docker pull grafana/grafana
sudo docker volume create grafana-data
sudo docker container run -v grafana-data -p 3000:3000 --name grafana --network network grafana/grafana



PublicIPv4DNS:3000


admin
admin

< rename as needed > 

select data source PublicIPv4DNS:9090
select metrics:
'run queries'

```
