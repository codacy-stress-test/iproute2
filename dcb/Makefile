# SPDX-License-Identifier: GPL-2.0
include ../config.mk

DCBOBJ = dcb.o \
         dcb_app.o \
         dcb_buffer.o \
         dcb_dcbx.o \
         dcb_ets.o \
         dcb_maxrate.o \
         dcb_pfc.o \
         dcb_apptrust.o \
         dcb_rewr.o
TARGETS += dcb
LDLIBS += -lm

all: $(TARGETS) $(LIBS)

dcb: $(DCBOBJ) $(LIBNETLINK)
	$(QUIET_LINK)$(CC) $^ $(LDFLAGS) $(LDLIBS) -o $@

install: all
	for i in $(TARGETS); \
	do install -m 0755 $$i $(DESTDIR)$(SBINDIR); \
	done

clean:
	rm -f $(DCBOBJ) $(TARGETS)
