LOCALEDIR ?= /usr/share/locale
TOMBFILE = LC_MESSAGES/tomb.mo

all:
	@rm -f tomb.pot
	@./generate_translatable_strings.sh > tomb.pot
	@echo "Strings generated in tomb.pot"
	@echo "\n WARNING!\n This script makes some mistakes you MUST fix by hand:\n * Reapeated msgids: remove them\n * msgids with \\\": They are most probably broken, look\n                   for the full strings in ../../tomb\n                   and replace them."


.PHONY: install
install: es.mo ru.mo fr.mo de.mo
	@install -Dm644 es.mo ${LOCALEDIR}/es/${TOMBFILE}
	@install -Dm644 ru.mo ${LOCALEDIR}/ru/${TOMBFILE}
	@install -Dm644 fr.mo ${LOCALEDIR}/fr/${TOMBFILE}
	@install -Dm644 de.mo ${LOCALEDIR}/de/${TOMBFILE}
	@echo "Translations installed."

%.mo: %.po
	msgfmt -o $@ $<

.PHONY: clean
clean:
	@rm -f *.mo
