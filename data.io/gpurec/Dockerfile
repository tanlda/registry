FROM tensorflow/tensorflow:latest-gpu-jupyter

RUN pip install tensorflow-datasets

RUN pip install tensorflow-recommenders

EXPOSE 8888

WORKDIR /home/jovyan/work

CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--allow-root", "--NotebookApp.token=''", "--no-browser"]
