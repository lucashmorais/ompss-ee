PROGRAM=stream-barr

TARGETS=$(PROGRAM)-p

JOB_SCHED_VERSION=-smp

BASE_DIR=../..
include $(BASE_DIR)/common-files/Makefile

CC = riscv64-unknown-linux-gnu-mcc 

CFLAGS = --ompss
CFLAGS_P = 
CFLAGS_I = --instrument
CFLAGS_D = --debug

LIBS  = 
INCS  = 

EXTRA = -std=c99 -O3 -Wall -Wno-unused -mcmodel=medany 

$(PROGRAM)-p: $(PROGRAM).c
	$(CC) $(GFLAGS) $(CFLAGS) $(CFLAGS_P) $(EXTRA) $(INCS) -o $@ $< $(LIBS)

$(PROGRAM)-i: $(PROGRAM).c
	$(CC) $(GFLAGS) $(CFLAGS) $(CFLAGS_I) $(EXTRA) $(INCS) -o $@ $< $(LIBS)

$(PROGRAM)-d: $(PROGRAM).c
	$(CC) $(GFLAGS) $(CFLAGS) $(CFLAGS_D) $(EXTRA) $(INCS) -o $@ $< $(LIBS)

clean:
	rm -f $(CC)_* *.o *~ $(TARGETS) 

