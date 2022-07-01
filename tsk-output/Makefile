all: t.com t.tsk

lib.bin: lib.mac
	zxcc zsm4 -"=lib/l"
	zxcc drlink lib.bin=lib
	rm lib.rel lib.sym

t.t: mklib.t t.src lib.bin
	zxcc ./bin/t3xz16 mklib
	zxcc mklib

t.com: t.t
	zxcc ./bin/t3xz16 t

t.tsk: t.t t.com
	cp t.t t.t3x
	zxcc t t

test:
	zxcc t t
	cp t.com t1.com
	zxcc t t
	comp t.com t1.com
	cp t.com t.bin.new

clean:
	rm -f *~ *.prn t.com t.tsk lib.bin
