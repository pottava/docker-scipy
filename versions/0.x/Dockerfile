# SciPy v0.18.1 & NumPy v1.11.3
#
# docker run --rm -it pottava/scipy:0.18
# docker run --rm pottava/scipy:0.18 -c 'import scipy; scipy.show_config()'

FROM alpine:3.5

ENV BLAS=/usr/lib/libblas.so \
    LAPACK=/usr/lib/liblapack.so

RUN apk --no-cache add openblas lapack libstdc++ python3 \
    && apk --no-cache add --virtual build-deps \
        lapack-dev python3-dev g++ gfortran \
        ca-certificates \
    && pip3 install --upgrade pip setuptools \
    && ln -s /usr/bin/python3 /usr/bin/python \
    && ln -s /usr/include/locale.h /usr/include/xlocale.h \
    && pip3 install scipy \
    && apk del --purge -r build-deps \
    && rm -r /root/.cache

ENTRYPOINT ["/usr/bin/python3"]
CMD ["-c", "'import scipy; print(scipy.__version__)'"]
