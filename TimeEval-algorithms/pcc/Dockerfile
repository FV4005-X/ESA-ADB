FROM registry.gitlab.hpi.de/akita/i/pyod-1.1.2

LABEL maintainer="sebastian.schmidl@hpi.de"

ENV ALGORITHM_MAIN="/app/algorithm.py"


# install algorithm dependencies
COPY requirements.txt .
RUN pip install -r ./requirements.txt

COPY algorithm.py .
