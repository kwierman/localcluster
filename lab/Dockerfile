# builder step used to download and configure spark environment
FROM bde2020/spark-master:2.1.0-hadoop2.8-hive-java8

# Add Dependencies for PySpark
RUN apt-get update && apt-get install -y curl vim wget software-properties-common ssh net-tools ca-certificates python3 python3-pip python3-numpy python3-matplotlib python3-scipy python3-pandas python3-simpy python3-cffi
RUN update-alternatives --install "/usr/bin/python" "python" "$(which python3)" 1


# Fix the value of PYTHONHASHSEED
# Note: this is needed when you use Python 3.3 or greater
ENV PYTHONHASHSEED=1

RUN pip3 install pyspark==${SPARK_VERSION}

# -- Layer: JupyterLab
RUN apt install libffi-dev
RUN pip3 install jupyterlab==2.1.5 pyspark==${SPARK_VERSION}

# -- Runtime

EXPOSE 8888
WORKDIR /opt/spark-data
CMD jupyter lab --ip=0.0.0.0 --port=8888 --no-browser --allow-root --NotebookApp.token=