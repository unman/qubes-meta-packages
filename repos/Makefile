install-vm-debian:
	install -d $(DESTDIR)/etc/apt/sources.list.d
	sed -e "s/@DIST@/`lsb_release -cs`/" qubes-contrib-r4.0.list.in \
		> $(DESTDIR)/etc/apt/sources.list.d/qubes-contrib-r4.0.list
	install -d $(DESTDIR)/etc/apt/trusted.gpg.d
	gpg --no-default-keyring --keyring \
		$(DESTDIR)/etc/apt/trusted.gpg.d/qubes-4-contrib-keyring.gpg \
		--import qubes-contrib-debian-4.asc

install-vm-fedora: install-fedora
	install -d $(DESTDIR)/etc/yum.repos.d
	install -m 0644 qubes-contrib-vm-r4.0.repo $(DESTDIR)/etc/yum.repos.d

install-fedora:
	install -d $(DESTDIR)/etc/pki/rpm-gpg/
	install -m 0644 qubes-contrib-fedora-4.asc \
		$(DESTDIR)/etc/pki/rpm-gpg/RPM-GPG-KEY-qubes-4-contrib
	ln -s RPM-GPG-KEY-qubes-4-contrib \
		$(DESTDIR)/etc/pki/rpm-gpg/RPM-GPG-KEY-qubes-4.0-contrib
