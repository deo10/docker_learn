
docker stack ps webapp - list of tasks are running on webapp stack

docker stack ls - To list stacks

docker stack deploy --compose-file file.yaml STACK_NAME - to run docker stack

docker stack rm - remove stack

docker stack services - list stack services

---
docker stack deploy - Deploy a new stack or update an existing stack. Example:
docker stack deploy --compose-file docker-compose.yml my_stack
docker stack ls - List all stacks. Example:
docker stack ls

docker stack services - List the services in the stack. Example:
docker stack services my_stack

docker stack ps - List the tasks in the stack. Example:
docker stack ps my_stack

docker stack rm - Remove one or more stacks. Example:
docker stack rm my_stack

docker stack inspect - Display detailed information on one or more stacks. Example:
docker stack inspect my_stack