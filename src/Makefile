export INCLUDE_PATH
CXXFLAGS = -I$(INCLUDE_PATH) -O2

all: judger run_program

% : %.cpp
	$(CXX) $(CXXFLAGS) $< -o $@
