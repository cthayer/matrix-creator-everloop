# Matrix Creator - Everloop

This is an example everloop program running in a docker container that uses the Matrix Creator attached to a raspberry pi.

## Run

```bash
docker run \
  -v /usr/include/matrix_hal:/usr/include/matrix_hal \
  -v /usr/lib/libmatrix_creator_hal.so:/usr/lib/libmatrix_creator_hal.so \
  -v /usr/lib/libwiringPi.so:/usr/lib/libwiringPi.so \
  -v /usr/lib/libwiringPiDev.so:/usr/lib/libwiringPiDev.so \
  --device=/dev/spidev0.0:/dev/spidev0.0 \
  cdmnky/matrix-everloop:1.0.2-arm32v7
```
Stop the container by running the following command in another terminal:
```bash
docker kill -s SIGINT <container_id>
```
### Pre-Requisites

#### Hardware
* Raspberry Pi (3b or 4 is suggested)
* [Matrix Creator](https://www.matrix.one/products/creator)

#### Software
* [Matrix Hal](https://matrix-io.github.io/matrix-documentation/matrix-hal/getting-started/installation-package/) must be installed on the host system
* Docker must be installed on the host system

## Build

Building the docker container must be done on a raspberry pi with [Matrix Hal](https://matrix-io.github.io/matrix-documentation/matrix-hal/getting-started/installation-package/) already installed.

```bash
packer build packer.json
```

### Pre-Requisites

#### Hardware
* Raspberry Pi (3b or 4 is suggested)
* [Matrix Creator](https://www.matrix.one/products/creator)

#### Software
* [Matrix Hal](https://matrix-io.github.io/matrix-documentation/matrix-hal/getting-started/installation-package/) must be installed on the host system
* Docker must be installed on the host system
* [Packer](https://packer.io/) must be installed on the host system
