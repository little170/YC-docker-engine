This YC-docker-engine is modified from [Moby](https://github.com/moby/moby) project

1. You need to modify layer/layer_store.go line 440 to your own path
2. Start the original docker engine
```
sudo /etc/init.d/docker start
```
3. Build compile environment
```
make build
```
4. Compile the new docker engine
```
make binary
```
5. Stop the original docker engine
```
sudo /etc/init.d/docker stop
```
6.start the new docker engine
```
sudo bundles/binary-daemon/dockerd
```
7. try if can delete the top layer of image
```
docker rmi <image:tag>
```

8. you can modify the num of layer you want to delete. 
 Simply modify the num in "delete_layer_num"
