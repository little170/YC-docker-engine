1. Modify from [Moby](https://github.com/moby/moby) project
2. You need to modify layer/layer_store.go line 440 to your own path
3. Start the original docker engine
```
sudo /etc/init.d/docker start
```
4. Build compile environment
```
make build
```
5. Compile the new docker engine
```
make binary
```
6. Stop the original docker engine
```
sudo /etc/init.d/docker stop
```
7.start the new docker engine
```
sudo bundles/binary-daemon/dockerd
```
8. try if can delete the top layer of image
```
docker rmi <image:tag>
```

9. you modify the num of layer you want to delete 
simply modify the num in "delete_layer_num"
