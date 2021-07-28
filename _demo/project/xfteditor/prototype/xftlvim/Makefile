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
	sudo install -Dm755 ./xftlvim /usr/local/bin/xftlvim
	sudo install -Dm644 ./xftlvim.desktop /usr/share/applications/xftlvim.desktop
.PHONY: install

remove:
	sudo rm -f /usr/local/bin/xftlvim
	sudo rm -f /usr/share/applications/xftlvim.desktop
.PHONY: remove
