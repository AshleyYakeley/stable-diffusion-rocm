# Stable Diffusion Dockerfile for ROCm

Run Stable Diffusion on an AMD card, using [this method](https://www.youtube.com/watch?v=d_CgaHyA_n4). Tested on my RX 6900 XT.

1. Obtain `sd-v1-4.ckpt` and put it in `rocm/`
1. Run `./build-rocm` to build the Docker image
1. Run `./run-rocm` to run a shell in the Docker container
1. Inside the container, you can do e.g. `python scripts/txt2img.py --outdir /output --plms --prompt "a unicorn riding a purple tricycle"`
