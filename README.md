# Stable Diffusion Dockerfile for ROCm

Run Stable Diffusion on an AMD card, using [this method](https://www.youtube.com/watch?v=d_CgaHyA_n4). Tested on my RX 6700 (non XT).
Uses [basujindal's stable diffusion fork](https://github.com/basujindal/stable-diffusion) for lower memory usage.

1. Obtain `sd-v1-4.ckpt` and put it in `rocm/`
1. Run `./build-rocm` to build the Docker image
1. Run `./run-rocm` to run a shell in the Docker container
1. Inside the container, you can run commands to generate images like: `python optimizedSD/optimized_txt2img.py --outdir /output --prompt "a unicorn riding a purple tricycle"`
