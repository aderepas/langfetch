PREFIX = /usr
SHAREDIR = ${PREFIX}/share
MANDIR = ${SHAREDIR}/man

all:
	@echo "Run 'make install' to install langfetch."

install:
	@cp main.py old_main.py
	@/usr/bin/python replace.py
	# Create the directorys if they don't exist
	@mkdir -p $(DESTDIR)$(PREFIX)/bin
	@mkdir -p $(DESTDIR)$(MANDIR)/man1
	@mkdir -p $(DESTDIR)$(SHAREDIR)/langfetch
	# Copy files
	@cp -p main.py $(DESTDIR)$(PREFIX)/bin/langfetch
	@chmod 755 $(DESTDIR)$(PREFIX)/bin/langfetch
	@cp -p languages.json ${DESTDIR}$(SHAREDIR)/langfetch/languages.json
	# Restore files
	@rm main.py
	@mv old_main.py main.py

uninstall:
	@rm -rf $(DESTDIR)$(PREFIX)/bin/langfetch
	@rm -rf $(DESTDIR)$(SHAREDIR)/langfetch
