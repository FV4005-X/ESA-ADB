FROM registry.gitlab.hpi.de/akita/i/python3-base as build

COPY anomalydetector /app/anomalydetector

RUN set -eux; \
    apt-get update; \
    apt-get install -y --no-install-recommends libfftw3-dev build-essential; \
    apt-get clean; \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN pip install Cython
RUN cd /app/anomalydetector/; python setup.py install

FROM registry.gitlab.hpi.de/akita/i/python3-base as eval

LABEL maintainer="phillip.wenig@hpi.de"

ENV ALGORITHM_MAIN="/app/algorithm.py"

COPY --from=build /usr/local/lib/python3.7/site-packages /usr/local/lib/python3.7/site-packages
COPY algorithm.py /app/
