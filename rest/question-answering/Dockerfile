FROM achangnovetta/adaptnlp:latest

# For SSL/TLS for requests
ENV REQUESTS_CA_BUNDLE /etc/ssl/certs/ca-certificates.crt
ENV SERVER_PORT 5000
ENV SERVER_HOST 0.0.0.0

# Default ARG vars for model configuration
ARG QUESTION_ANSWERING_MODEL=distilbert-base-uncased-distilled-squad

ENV QUESTION_ANSWERING_MODEL ${QUESTION_ANSWERING_MODEL}

# Expose typical endpoints
EXPOSE 8888
EXPOSE 5000

WORKDIR /adaptnlp-rest

COPY . /adaptnlp-rest

RUN pip3 install -r requirements.txt

RUN chmod +x ./entrypoint.sh

ENTRYPOINT ["./entrypoint.sh"]
