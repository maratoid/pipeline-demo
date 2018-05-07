FROM python:3-alpine
LABEL authors="Marat Garafutdinov<maratoid@gmail.com>"

ARG GIT_COMMIT=SOME-DEFAULT
ARG JOB_NAME=SOME-DEFAULT

RUN echo "GIT_COMMIT=${GIT_COMMIT}"
RUN echo "JOB_NAME=${JOB_NAME}"

COPY scripts/dockerScript.sh /dockerScript.sh
RUN chmod +x dockerScript.sh
RUN /dockerScript.sh

RUN apk add -U ca-certificates libffi libstdc++ && \
    apk add --virtual build-deps build-base libffi-dev && \
    # Pip
    pip install --no-cache-dir gunicorn /httpbin && \
    # Cleaning up
    apk del build-deps && \
    rm -rf /var/cache/apk/*

EXPOSE 8080

CMD ["gunicorn", "-b", "0.0.0.0:8080", "httpbin:app"] 