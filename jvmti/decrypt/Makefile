ifeq ($(shell uname), Linux)
  CC         = g++ 
  LIBLINK    = -shared 
  INCLUDEDIR = -I/usr/java/jdk1.8.0_171-amd64/include -I/usr/java/jdk1.8.0_171-amd64/include/linux
  TARGET     = libdecrypt.so
endif

ifeq ($(shell uname), Darwin)
  CC		 = g++ 
  LIBLINK    = -dynamiclib
  TARGET     = libdecrypt.dylib
  INCLUDEDIR = -I/Library/Java/JavaVirtualMachines/jdk1.8.0_172.jdk/Contents/Home/include -I/Library/Java/JavaVirtualMachines/jdk1.8.0_172.jdk/Contents/Home/include/darwin
endif

OBJS = decrypt.o

$(TARGET):$(OBJS)
	$(CC) $(LIBLINK) -o $(TARGET) $(OBJS)

decrypt.o: decrypt.cpp
	$(CC) $(INCLUDEDIR) -c decrypt.cpp

.PHONY:clean
clean:
	rm $(TARGET) $(OBJS)