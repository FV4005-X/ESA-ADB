FROM registry.gitlab.hpi.de/akita/i/python3-base

LABEL maintainer="phillip.wenig@hpi.de"

ENV ALGORITHM_MAIN="/app/algorithm.py"

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY health_esn ./health_esn
COPY algorithm.py .
