LIBRARY := libfast-dnn.so
EXECUTABLE := fast-dnn
PROJECT_HOME := ../..
OBJFILES := dnn.o jni_dnn.o float_dnn.o
JNI_HEADERS :=../../include/linux
INCLUDES := -I$(JNI_HEADERS)
CXXFLAGS := $(INCLUDES) -g -Wall -O2 -march=native -mtune=native -std=c++11 -funroll-loops -msse4 -fPIC

all : $(EXECUTABLE) $(LIBRARY)
	@echo $(EXECUTABLE) and $(LIBRARY) created.

clean :
	rm -f $(OBJFILES) $(EXECUTABLE) $(LIBRARY)
	@echo All Clean.

$(EXECUTABLE): $(OBJFILES)
	$(CXX) -o $(EXECUTABLE) $^

$(LIBRARY): $(OBJFILES)
	$(CXX) -shared -static-libstdc++ -o $@ $^
	cp $@ $(PROJECT_HOME)/src/java/resources
