# Pandas with SciPy & Jupyter notebook
#
# docker run --rm -it -p 80:8888 pottava/pandas:0.19

FROM pottava/scipy:0.18-notebook

ENV MATPLOTLIB_VERSION=2.0.0rc2 \
    PANDAS_VERSION=0.19.2

RUN apk --no-cache add freetype \
    && apk --no-cache add --virtual build-deps g++ python3-dev freetype-dev \
    && pip3 install "matplotlib == ${MATPLOTLIB_VERSION}" \
    && pip3 install "pandas == ${PANDAS_VERSION}" \
    && apk del --purge -r build-deps \
    && rm -r /root/.cache
