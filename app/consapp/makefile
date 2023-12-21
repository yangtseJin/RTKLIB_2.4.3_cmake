#
# make all cui applications by gcc
#
#export CC = clang
export CC = gcc

#BINDIR = /usr/local/bin
BINDIR = /home/jin/my_ws/rtklib_study/RTKLIB-rtklib_2.4.3/bin
DIRS   = pos2kml str2str rnx2rtkp convbin rtkrcv

all:
	@for i in $(DIRS); do make -C $$i/gcc; done

install:
	@echo installing...
	@for i in $(DIRS); do cp $$i/gcc/$$i $(BINDIR); done

clean:
	@echo cleaning up...
	@for i in $(DIRS); do make -C $$i/gcc clean; done

