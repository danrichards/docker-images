# Docker Images

These are the files used for building the custom images with PHP.

There are Makefiles stored in each folder with commands for building and pushing.  

**If you make changes to the php/node version in the Dockerfiles, change the version in the Makefile so you don't overwrite the existing ones**  

You need your Docker CLI to be logged in to the `danrichardsri` Docker account to upload the images. 

## Updating an Image (example)

- Update `Dockerfile` as needed
- Run `make build`
- Run `make push`

### Then, advise your peers, on their local, to ...

- Run `dc pull worker` 
- And `dc down`
- And finally `dc up -d`