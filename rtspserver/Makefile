PROGRAM = barsntone snp6200 videoServer
PROGRAM_FILES = barsntone.c snp6200.c

CFLAGS = $(shell pkg-config --cflags  gstreamer-1.0 gstreamer-rtsp-1.0  gstreamer-rtsp-server-1.0) 
LIBS = $(shell pkg-config --libs  gstreamer-1.0 gstreamer-rtsp-1.0  gstreamer-rtsp-server-1.0) 

CPPFLAGS += -I. -I$(top_builddir)/include -I/usr/include/gstreamer-1.0 -I/usr/include/glib-2.0 -I/usr/lib/i386-linux-gnu/glib-2.0/include -I/usr/include/libxml2 -I/usr/include/gstreamer-1.0/gst/rtsp-server/
 
all:  barsntone snp6200 videoServer mixstream

barsntone: barsntone.c 
	$(CC) barsntone.c $(CFLAGS) $(LDFLAGS) -o barsntone $(LIBS)

snp6200: snp6200.c
	$(CC) snp6200.c $(CFLAGS) $(LDFLAGS) -o snp6200 $(LIBS)

videoServer: videoServer.c
	$(CC) videoServer.c $(CFLAGS) $(LDFLAGS) -o videoServer $(LIBS)

mixstream: mixstream.c
	$(CC) mixstream.c $(CFLAGS) $(LDFLAGS) -o mixstream $(LIBS)

clean:
	rm -f *.o *.ts
	rm -f $(PROGRAM)

