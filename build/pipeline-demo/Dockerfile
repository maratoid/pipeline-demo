FROM busybox
LABEL authors="Marat Garafutdinov<maratoid@gmail.com>"

ARG GIT_COMMIT=SOME-DEFAULT
ARG JOB_NAME=SOME-DEFAULT
ARG SECRET_ARG=SOME-DEFAULT

RUN echo "GIT_COMMIT=${GIT_COMMIT}"
RUN echo "JOB_NAME=${JOB_NAME}"
RUN echo "SECRET_ARG=${SECRET_ARG}"

COPY testfromscript.sh /testfromscript.sh
COPY testfrominline.sh /testfrominline.sh

RUN ls 
RUN chmod +x /testfromscript.sh
RUN chmod +x /testfrominline.sh
RUN /testfromscript.sh
RUN /testfrominline.sh

COPY scripts/dockerScript.sh /dockerScript.sh
RUN chmod +x dockerScript.sh
RUN /dockerScript.sh