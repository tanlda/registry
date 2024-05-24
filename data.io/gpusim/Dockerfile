FROM nvidia/cuda:11.8.0-devel-ubuntu22.04

RUN apt-get update && \
    apt-get install -y software-properties-common && \
    add-apt-repository ppa:deadsnakes/ppa && apt-get update && \
    apt-get install -y python3.10 python3.10-dev python3.10-distutils python3.10-venv python3-pip wget && \
    apt-get clean

RUN pip install --extra-index-url https://pypi.nvidia.com tensorrt-bindings==8.6.1 tensorrt-libs==8.6.1 tensorflow[and-cuda]==2.15.0

RUN pip install tensorflow_similarity

RUN pip install tensorflow-addons

RUN pip install mlflow

RUN pip install jupyter

EXPOSE 8888

WORKDIR /home/jovyan/work

CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--allow-root", "--NotebookApp.token=''", "--no-browser"]
