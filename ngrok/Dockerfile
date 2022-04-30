FROM alpine:latest
# Install unzip & curl for downloading and installing ngrok
RUN apk add curl unzip
# Download ngrok, unzip, & move to /usr/local/bin
RUN cd /tmp \
	&& curl https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-amd64.zip --output ngrok.zip \
	&& unzip ngrok.zip \
	&& mv ngrok /usr/local/bin/ngrok
# Run ngrok with mounted config file
CMD ngrok start --config=/opt/ngrok/conf/ngrok.yml --all --log "stdout" --log-level "debug"
