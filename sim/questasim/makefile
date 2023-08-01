all: 
	make compile; make simulate;
compile: 
	vlib work; 
	vlog -sv \
	+acc \
	+cover \
	+fcover \
	-l ram_compile.log \
	-f ../ram_compile.f 

simulate:
	vsim -vopt \
	work.top \
	work.RAM \
	-voptargs=+acc=npr \
	-assertdebug \
	-l ram_test.log \
	-sva \
  -coverage \
	-c -do " run -all; exit" \

clean:
	rm -rf *.log
