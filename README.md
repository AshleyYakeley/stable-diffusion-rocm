# Stable Diffusion Dockerfile for ROCm

Run Stable Diffusion on an AMD card, using [this method](https://www.youtube.com/watch?v=d_CgaHyA_n4). Tested on my RX 6700 (non XT).

1. Obtain `sd-v1-4.ckpt` and put it in `rocm/`
1. Run `./build-rocm` to build the Docker image
1. Run `./run-rocm` to run a shell in the Docker container
1. Inside the container, you can do e.g. `python scripts/txt2img.py --outdir /output --plms --prompt "a unicorn riding a purple tricycle" --H 256 --W 512`

_NB: You cannot run this at 512/512 resolution or higher on a 10GB card as it will run out of video memory. Running at lower resolutions like 256/256 will lead to strange artifacts in the output._
