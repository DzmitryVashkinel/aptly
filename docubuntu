FROM redhat/ubi8-minimal

COPY aptly_ubuntu.conf aptly_debian.conf regula.gpg /home/

RUN apt update && apt install -y --no-install-recommends apt-utils apt-transport-https wget software-properties-common ; \
	## ADD REPO APTLY \
	wget -qO - https://www.aptly.info/pubkey.txt | sudo apt-key add -; \
	apt-add-repository "deb http://repo.aptly.info/ squeeze main"; \
	# Install software \
	apt install -y aptly expect lftp gpg gpg-agent gpgconf;\
	# Remove trash \
	apt clean && rm -rf /var/lib/apt/lists/* /tmp/*

CMD ["/bin/bash"]