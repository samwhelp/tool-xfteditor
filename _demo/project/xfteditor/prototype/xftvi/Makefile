default: help
.PHONY: default

help:
	@echo 'Usage:'
	@echo '	$$ make [action]'
	@echo
	@echo 'Example:'
	@echo '	$$ make'
	@echo '	$$ make help'
	@echo
	@echo '	$$ make install'
	@echo
.PHONY: help


install:
	sudo install -Dm755 ./xftvi /usr/local/bin/xftvi
	sudo install -Dm644 ./xftvi.desktop /usr/share/applications/xftvi.desktop
.PHONY: install

remove:
	sudo rm -f /usr/local/bin/xftvi
	sudo rm -f /usr/share/applications/xftvi.desktop
.PHONY: remove
