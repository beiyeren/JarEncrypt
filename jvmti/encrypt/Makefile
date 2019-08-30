ifeq ($(shell uname), Linux)
  CC         = g++ 
  LIBLINK    = -shared -fPIC
  INCLUDEDIR = -I/usr/java/jdk1.8.0_171-amd64/include -I/usr/java/jdk1.8.0_171-amd64/include/linux
  TARGET     = libencrypt.so
endif

ifeq ($(shell uname), Darwin)
  CC		 = g++ 
  LIBLINK    = -dynamiclib
  TARGET     = libencrypt.dylib
  INCLUDEDIR = -I/Library/Java/JavaVirtualMachines/jdk1.8.0_172.jdk/Contents/Home/include -I/Library/Java/JavaVirtualMachines/jdk1.8.0_172.jdk/Contents/Home/include/darwin
endif

OBJS = encrypt.o

$(TARGET):$(OBJS)
	$(CC) $(LIBLINK) -o $(TARGET) $(OBJS)

encrypt.o: encrypt.cpp
	$(CC) $(INCLUDEDIR) -c encrypt.cpp

.PHONY:clean
clean:
	rm $(TARGET) $(OBJS)