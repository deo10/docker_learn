url
https://github.com/dockersamples/example-voting-app.git

Running app using separate containers connected by --link
https://kodekloud.com/topic/example-for-voting-application/

git clone

cd /home/admin/example-voting-app/vote
cat Dockerfile
docker build . -t voting-app
docker image ls

docker run -d --name=redis redis
docker run -d -p=5000:80 --name=voting-app --link redis:redis voting-app

docker run -d --name=db -e POSTGRES_PASSWORD=password postgres:9.4

cd /home/admin/example-voting-app/worker
docker build . -t worker-app
docker run -d --name=worker-app --link redis:redis --link db:db worker-app

cd /home/admin/example-voting-app/result
docker build . -t result-app
docker run -d -p 5001:80 --name=result-app --link db:db result-app
