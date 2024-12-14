ACLOCAL_AMFLAGS = -I m4 --install

SOURCEDIR=src
SOURCES := $(shell find $(SOURCEDIR) -name '*.c')
OBJS = $(patsubst src/%.c,obj/%.o,$(SOURCES))

# overwrite c flags to enable debugging
CFLAGS+=-Wall

all: bin/$(PACKAGE)

bin/$(PACKAGE): $(SOURCES)
	mkdir -p bin
	$(CC) -o $@ $(CFLAGS) $(SOURCES)

clean-local:
	rm -f bin/$(PACKAGE)

install-exec-local:
	install -m 0755 $(@D)/bin/$(PACKAGE) $(TARGET_DIR)/usr/sbin/$(PACKAGE)
