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
	sudo install -Dm755 ./xftnvim /usr/local/bin/xftnvim
	sudo install -Dm644 ./xftnvim.desktop /usr/share/applications/xftnvim.desktop
.PHONY: install

remove:
	sudo rm -f /usr/local/bin/xftnvim
	sudo rm -f /usr/share/applications/xftnvim.desktop
.PHONY: remove
