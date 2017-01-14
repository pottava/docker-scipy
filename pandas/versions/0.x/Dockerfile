# Pandas with SciPy & Jupyter notebook
#
# docker run --rm -it pottava/pandas:0.19 ipython
# docker run --rm -it -p 80:8888 pottava/pandas:0.19

FROM pottava/scipy:0.18-notebook

ENV MATPLOTLIB_VERSION=2.0.0rc2 \
    PANDAS_VERSION=0.19.2

RUN apk --no-cache add freetype \
    && apk --no-cache add --virtual build-deps g++ python3-dev freetype-dev \

    # Install Matplotlib for 2D plotting
    && pip3 install "matplotlib == ${MATPLOTLIB_VERSION}" \

    # Install Pandas
    && pip3 install "pandas == ${PANDAS_VERSION}" \

    # Clean up
    && find / -type d -name tests -depth -exec rm -rf {} \; \
    && find / -type d -name test -depth -exec rm -rf {} \; \
    && find / -type d -name \__pycache__ -depth -exec rm -rf {} \; \
    && find / -type d -name '*.egg-info' -depth -exec rm -rf {} \; \
    && apk del --purge -r build-deps \
    && rm -rf /root/.cache
