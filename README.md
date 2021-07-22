API Documentation
=================

### How to build

```
docker run --rm --name slate -v $(pwd)/build:/srv/slate/build -v $(pwd)/source:/srv/slate/source slatedocs/slate
```

### How to run

```
docker run --rm --name slate -p 4567:4567 -v $(pwd)/source:/srv/slate/source slatedocs/slate serve
```

Documentation is now available [here](http://localhost:4567)


### If the documentation is not updated after merging, run the following command
```
./deploy.sh --push-only
```
