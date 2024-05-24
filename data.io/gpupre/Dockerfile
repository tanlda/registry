FROM nvidia/cuda:11.8.0-devel-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y software-properties-common && \
    add-apt-repository ppa:deadsnakes/ppa && apt-get update && \
    apt-get install -y python3.11 python3.11-dev python3.11-distutils python3.11-venv python3-pip wget && \
    apt-get clean

RUN apt-get update && \
    apt-get install -y graphviz

RUN pip install jupyter numpy pandas tqdm

RUN pip install dask[complete] dask-kubernetes graphviz

RUN pip install --extra-index-url=https://pypi.nvidia.com cudf-cu11 dask-cudf-cu11

RUN pip install cupy-cuda11x

EXPOSE 8888

WORKDIR /home/jovyan/work

CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--allow-root", "--NotebookApp.token=''", "--no-browser"]
