SUBDIRS := $(wildcard */.)

all: $(SUBDIRS)

.PHONY: clean $(SUBDIRS)

$(SUBDIRS):
	$(MAKE) -C $@

clean:
	for dir in $(SUBDIRS); do \
        $(MAKE) -C $$dir clean; \
    done


