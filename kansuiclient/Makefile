PREFIX?=/opt/sensprout
CC=gcc

IRRIGATION_CLIENT=sensprout_irrigation
IRRIGATION_OBJ=cfwdipc.o chkcmd.o easyhttpclient.o kansuiclient.o myfifo.o mythread.o mytimer.o readcfg.o wscclient.o  ysleep.o

#PORTON=porton
#PORTON_OBJ=porton.o
#PORTOFF=portoff
#PORTOFF_OBJ=portoff.o
#iTIMERLIST=mytimer.csv

CFLAGS=-I. -O0 -g 
LIBS=-lpthread -lm -lrt -ldl -lwiringPi

all: $(IRRIGATION_CLIENT) $(PORTON) $(PORTOFF)

$(IRRIGATION_CLIENT): $(IRRIGATION_OBJ)
	$(CC) $(LDFLAGS) -o $@ $^ $(LIBS)

#$(PORTON): $(PORTON_OBJ)
#	$(CC) $(LDFLAGS) -o $@ $^ $(LIBS)

#$(PORTOFF): $(PORTOFF_OBJ)
#	$(CC) $(LDFLAGS) -o $@ $^ $(LIBS)

#install: all
#	mkdir -p $(PREFIX)
#	mkdir -p $(PREFIX)/bin
#	#install wsclient
#	cp $(IRRIGATION_CLIENT) $(PREFIX)/bin
#	chmod 755 $(PREFIX)/bin/$(IRRIGATION_CLIENT)
#	cp $(PORTON) $(PREFIX)/bin
#	cp $(PORTOFF) $(PREFIX)/bin
#	cp $(TIMERLIST) $(PREFIX)/bin


#uninstall:
#	rm -rf $(PREFIX)

clean:
	rm -rf $(IRRIGATION_CLIENT) $(PORTON) $(PORTOFF) $(IRRIGATION_OBJ) $(PORTON_OBJ) $(PORTOFF_OBJ)

.PHONY: install uninstall clean
