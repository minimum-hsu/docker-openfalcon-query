# docker-openfalcon-query

## Build

Enter the following command in the repo directory.

```
$sudo docker build --force-rm=true -t openfalcon-query .
```

## Run

### Basic Run

Use default configuration, and falcon-query package.

```
$sudo docker run -dti --name query -p 9966:9966 openfalcon-query
```

### Advanced Run

+ Self-defined configuration

    Replace file **graph_backends.txt** in the volume */config*.  
    For more detail about **graph_backends.txt**, see [Query](http://book.open-falcon.com/zh/install/query.html).

+ New falcon-query package

    Replace file **falcon-query.tar.gz** in the volume */package*.
  
For example, **graph_backends.txt** in /tmp/config and **falcon-query.tar.gz** in /tmp/pack,

```
$sudo docker run -dti --name query -v /tmp/pack:/package -v /tmp/config/graph_backends.txt:/config/graph_backends.txt -p 9966:9966 openfalcon-query
```
