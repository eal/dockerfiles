# Ubuntu Xenial / Python 2 / IPython Notebook / GraphLab

FROM ubuntu:xenial
MAINTAINER datatyp

RUN apt-get update
RUN apt-get -y dist-upgrade

# Basic python setup
RUN apt-get -y install python
RUN apt-get -y install python-pip

# numpy & friends
# RUN apt-get -y build-dep python-pandas python-scipy python-matplotlib python-matplotlib
# RUN pip install scipy
# RUN pip install pandas
# RUN pip install matplotlib
# RUN pip install bokeh

#RUN pip install SFrame
COPY GraphLab_Create-1.8.4-py2-none-any.whl /root/
COPY .graphlab /root/
RUN pip install setuptools
RUN pip install /root/GraphLab_Create-1.8.4-py2-none-any.whl

# ipython notebook
# RUN apt-get -y build-dep python-zmq
# RUN pip install pyzmq
# RUN pip install jinja2
# RUN pip install tornado
# RUN pip install jsonschema
RUN pip install "ipython[notebook]"

#mathjax stuff
# RUN echo 'from IPython.external import mathjax; mathjax.install_mathjax()' | python

# Other useful tools
RUN apt-get install -y jq curl

EXPOSE 8888
CMD jupyter notebook --ip 0.0.0.0 --no-browser
#CMD ["jupyter", "notebook", "--ip", "0.0.0.0", "--no-browser"]
