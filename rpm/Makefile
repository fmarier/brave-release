all: source
		for dist in epel-7-x86_64 \
				    fedora-27-x86_64 \
				    fedora-28-x86_64 \
				    fedora-29-x86_64 \
					fedora-30-x86_64 ; do \
				mock -r $$dist \
				     --buildsrpm \
					 --source=brave-keyring-source.tar.gz \
					 --spec=brave-keyring.spec \
					 --rebuild \
					 --resultdir=output ; \
		done

keys:
		wget https://brave-browser-apt-release.s3.brave.com/brave-core.asc -O brave-keyring-1.3/etc/pki/rpm-gpg/RPM-GPG-KEY-brave

source: keys
		tar cvzf brave-keyring-source.tar.gz brave-keyring-1.3/*

clean:
		rm -rf output brave-keyring-source.tar.gz brave-keyring-1.3/etc/pki/rpm-gpg/*
