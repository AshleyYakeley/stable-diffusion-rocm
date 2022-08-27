FROM rocm/pytorch:rocm5.2_ubuntu20.04_py3.7_pytorch_1.11.0_navi21
RUN echo 2022-08-24 > /container.date
WORKDIR /dockerx
RUN pip3 install --upgrade pip
RUN conda update -y -n base -c defaults conda
RUN git clone --depth 1 -b uncensored https://github.com/AshleyYakeley/stable-diffusion.git .
RUN conda env create -f environment.yaml
RUN mkdir -p models/ldm/stable-diffusion-v1/
COPY sd-v1-4.ckpt models/ldm/stable-diffusion-v1/model.ckpt
RUN conda run -n ldm pip3 install --upgrade torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/rocm5.1.1
RUN conda run -n ldm python scripts/txt2img.py --help
ENTRYPOINT ["conda", "run", "-n", "ldm", "--no-capture-output"]
CMD /bin/bash
VOLUME /output
