# vault-consul-tutorial
Followed [this tutorial](https://medium.com/@pcarion/a-consul-a-vault-and-a-docker-walk-into-a-bar-d5a5bf897a87), but it didn't actually work. So I fixed it and now it works and all of the things are on the latest versions.

## Getting it up and running
 - have docker installed obvs
 - run `docker-compose up -d`
 - log into the docker bash.test `docker exec -it bash.test bash`
 - check that consul is working `consul members`
 - initialize vault `vault operator init`
 - Copy all of the keys and tokens it gives you into a file named keys (I put that file in the .gitignore)
 - unseal the vault `vault operator unseal`
 - This prompts you 3 times `Unseal Key (will be hidden):` (Use a different key each time it asks)
 - Use the root token that it gave you from the init and create an environment variable `export VAULT_TOKEN={ROOT_TOKEN}
 - Do vault things
