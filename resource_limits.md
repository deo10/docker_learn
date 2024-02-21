# CPU
# hard limit, but throtling
docker container run -itd --name=name_cont --cpus=2.5 ubuntu #container can use 2.5 cores from total number of cores
docker container run -itd --name=name_cont --cpuset-cpus="1" ubuntu #lock container to use only core #1
docker container inspect name | grep -i cpu

# MEM
# hard limit and OOM kill
docker container run -itd --name=name_cont --memory=512m ubuntu
docker container run -itd --name=name_cont --memory=512m --memory-swap=512m ubuntu
# Setting --memory-swap to the same value as --memory effectively disables swapping

docker container inspect name | grep -i mem

docker container run -itd --name=name_cont --memory=512m --memory-swap=-1 --memory-reservation=1000 ubuntu
# --memory-swap=-1 unlimited use of swap