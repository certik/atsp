F90 = gfortran
F90FLAGS = -Wall -std=legacy -Wextra -fPIC -Wno-unused -Wno-unused-dummy-argument
F90FLAGS += -g -fcheck=all

all: NONH TERMS GENCL HF MCHF BREIT CI ISO PLOTW PRINTW

NONH: NONH.o ANG.o COM.o NJGRAF.o RAD3.o
	$(F90) $(F90FLAGS) -o $@ $^

TERMS: TERMS.o
	$(F90) $(F90FLAGS) -o $@ $^

GENCL: GENCL.o
	$(F90) $(F90FLAGS) -o $@ $^

HF: HF.o
	$(F90) $(F90FLAGS) -o $@ $^

MCHF: MCHF.o COM.o RAD3.o
	$(F90) $(F90FLAGS) -o $@ $^

BREIT: BREIT.o ANG.o COM.o NJGRAF.o RAD3.o
	$(F90) $(F90FLAGS) -o $@ $^

CI: CI.o ANG.o COM.o NJGRAF.o RAD3.o
	$(F90) $(F90FLAGS) -o $@ $^

ISO: ISO.o COM.o RAD3.o
	$(F90) $(F90FLAGS) -o $@ $^

PLOTW: PLOTW.o
	$(F90) $(F90FLAGS) -o $@ $^

PRINTW: PRINTW.o
	$(F90) $(F90FLAGS) -o $@ $^

%.o: %.f
	$(F90) $(F90FLAGS) -c $<
