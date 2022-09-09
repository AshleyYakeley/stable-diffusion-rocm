FROM rocm/pytorch:rocm5.2_ubuntu20.04_py3.7_pytorch_1.11.0_navi21
RUN echo 2022-08-24 > /container.date
WORKDIR /sd
RUN pip3 install --upgrade pip
RUN conda update -y -n base -c defaults conda
RUN git clone --depth 1 https://github.com/basujindal/stable-diffusion .
RUN conda env create -f environment.yaml
RUN mkdir -p models/ldm/stable-diffusion-v1/
COPY sd-v1-4.ckpt models/ldm/stable-diffusion-v1/model.ckpt
RUN conda run -n ldm pip3 install --upgrade torch torchvision torchaudio gradio --extra-index-url https://download.pytorch.org/whl/rocm5.1.1
ENTRYPOINT ["conda", "run", "-n", "ldm", "--no-capture-output"]
CMD /bin/bash
VOLUME /output
EXPOSE 8080