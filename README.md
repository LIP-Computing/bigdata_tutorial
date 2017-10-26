# bigdata_tutorial
Tutorial docker and udocker

Build the docker image

```
docker build --no-cache=true -t keras-theano -f docker-keras-theano .
```

you can get examples of using keras by clonning the git repo

```
git clone https://github.com/fchollet/keras.git
```

make a dir to hold you python scripts and any input, after running the container
you will have the output results in the same dir

```
mkdir mydir
```

copy some examples of keras to that dir

```
cp keras/examples/* ~/mydir/
```

Run the container and mount the dir "mydir" in it

```
docker run -it -v $HOME/mydir:/home keras-theano /bin/bash
```

The container was built to have the default dir "/home" when you run the "bash"

Now inside the container

```
root@c6d0128e79bf:/home# ls -al
```

you see all the example scripts

root@c6d0128e79bf:/home# python3 imdb_cnn.py


