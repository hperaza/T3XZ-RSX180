# Path to Linux utilities
ZXCC    = zxcc

# Path to CP/M utilities
ZSM4    = ../bin/zsm4.com
LBR     = ../bin/lbr.com

SRCS = comp.mac \
	div.mac \
	mult.mac \
	strip.mac \
	start.mac \
	startcpm.mac \
	t.mac \
	tcpm.mac

OBJS = $(SRCS:.mac=.rel)

PROGS = t3xz.lib t3xzcpm.lib

all: $(PROGS)

.SUFFIXES:		# delete the default suffixes
.SUFFIXES: .mac .rel

$(OBJS): %.rel: %.mac
	$(ZXCC) $(ZSM4) -"="$</l/s8

t3xz.lib: $(OBJS)
	$(ZXCC) $(LBR) -"$@=t/e+start/e+comp/e+div/e+mult/e+strip/e"
	$(ZXCC) $(LBR) -",t3xz=t3xz.lib"
	$(ZXCC) $(LBR) -",tty:/m=t3xz.lib"

t3xzcpm.lib: $(OBJS)
	$(ZXCC) $(LBR) -"$@=tcpm/e+startcpm/e+comp/e+div/e+mult/e+strip/e"
	$(ZXCC) $(LBR) -",t3xzcpm=t3xzcpm.lib"
	$(ZXCC) $(LBR) -",tty:/m=t3xzcpm.lib"

clean:
	rm -f $(OBJS) $(PROGS) *.sym *.prn *.irl core *~ *.\$$\$$\$$
