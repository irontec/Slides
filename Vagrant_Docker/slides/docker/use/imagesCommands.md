##Images

#### List images

```bash
$docker images
```
    
#### Remove image

```bash
$ docker rmi repository|repository:tag|id
```
#### Save image

```bash
$ docker save -o image.tar repository|repository:tag|id 
$ docker save --output="image.tar" repository|repository:tag|id
```

#### Load image

```bash
$ docker load -i image.tar
$ docker load --input="image.tar"
```