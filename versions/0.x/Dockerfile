# SciPy v0.18.1 & NumPy v1.11.3
#
# docker run --rm -it pottava/scipy:0.18
# docker run --rm pottava/scipy:0.18 -c 'import scipy; print(scipy.__version__)'
# docker run --rm pottava/scipy:0.18 -c 'import scipy; scipy.show_config()'

FROM alpine:3.5

ENV SCIPY_VERSION=0.18.1 \
    BLAS=/usr/lib/libblas.so \
    LAPACK=/usr/lib/liblapack.so

RUN apk --no-cache add openblas lapack libstdc++ python3 ca-certificates \
    && apk --no-cache add --virtual build-deps lapack-dev python3-dev g++ gfortran \
    && ln -s /usr/include/locale.h /usr/include/xlocale.h \

    # Install SciPy
    && pip3 install "scipy == ${SCIPY_VERSION}" \

    # Clean up
    && find / -type d -name tests -depth -exec rm -rf {} \; \
    && find / -type d -name test -depth -exec rm -rf {} \; \
    && find / -type d -name \__pycache__ -depth -exec rm -rf {} \; \
    && find / -type d -name '*.egg-info' -depth -exec rm -rf {} \; \
    && apk del --purge -r build-deps \
    && rm -rf /root/.cache /usr/include/xlocale.h

ENTRYPOINT ["/usr/bin/python3"]
