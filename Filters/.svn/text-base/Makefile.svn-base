EXEC   = read

OBJS   = ./read_filters.o

INCL   = ./allvars.h ./proto.h  Makefile



#OPT   += -DSDSSIRAC
#OPT   += -DJOHNSONIRAC
OPT   += -DALLBANDS

#OPT += -DSALPETER2

#OPT += -DAPP
OPT += -DBC03
OPT += -DSALPETER

SYSTYPE = "Portsmouth"

CC       =   gcc -m64          # sets the C-compiler (default)
OPTIMIZE =   -O4 -Wall    # optimization and warning flags (default)



ifeq ($(SYSTYPE),"Portsmouth")
ifeq (PARALLEL,$(findstring PARALLEL,$(OPT)))
CC       =   gcc
else
CC       =   cc
endif
GSL_INCL = -I/opt/local/include
GSL_LIBS = -L/opt/local/lib 
endif


LIBS   =   -g -lm  $(GSL_LIBS) -lgsl -lgslcblas 

CFLAGS =   -g $(OPTIONS) $(OPT) $(OPTIMIZE) $(GSL_INCL)

$(EXEC): $(OBJS) 
	$(CC) $(OPTIMIZE) $(OBJS) $(LIBS)   -o  $(EXEC)  

$(OBJS): $(INCL) 


clean:
	rm -f $(OBJS)

tidy:
	rm -f $(OBJS) .$(EXEC)
