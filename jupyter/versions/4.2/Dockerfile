# SciPy with Jupyter notebook
#
# docker run --rm -p 80:8888 pottava/scipy:0.18-notebook

FROM pottava/scipy:0.18

RUN apk --no-cache add --virtual build-deps g++ python3-dev \
    && apk --no-cache add tini \
    && pip3 install jupyter \
    && apk del --purge -r build-deps \
    && rm -r /root/.cache

WORKDIR /root/notebook

ENTRYPOINT ["/sbin/tini", "--"]
CMD ["jupyter", "notebook", "--no-browser", "--port=8888", "--ip=0.0.0.0"]
