FROM busybox
LABEL authors="Marat Garafutdinov<maratoid@gmail.com>"

ARG GIT_COMMIT=SOME-DEFAULT
ARG JOB_NAME=SOME-DEFAULT

RUN echo "GIT_COMMIT=${GIT_COMMIT}"
RUN echo "JOB_NAME=${JOB_NAME}"

COPY testfromscript.txt /testfromscript.txt
COPY testfrominline.txt /testfrominline.txt

RUN ls 
RUN cat /testfromscript.txt
RUN cat /testfrominline.txt

COPY scripts/dockerScript.sh /dockerScript.sh
RUN chmod +x dockerScript.sh
RUN /dockerScript.sh