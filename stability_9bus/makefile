
CFLAGS	        = -g
FFLAGS	        =
CPPFLAGS        =
FPPFLAGS        =
LOCDIR          = src/ts/examples/tutorials/power_grid/stability_9bus/
EXAMPLESC       =  9bus_dm1.c 9bus_dm.c ex9bus.c ex9busadj.c ex9busopt.c ex9busopt_fd.c
EXAMPLESF       =
EXAMPLESFH      =
MANSEC          = TS
DIRS            =

include ${PETSC_DIR}/lib/petsc/conf/variables
include ${PETSC_DIR}/lib/petsc/conf/rules

9bus_dm: 9bus_dm.o  chkopts
	-${CLINKER} -o 9bus_dm 9bus_dm.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm.o
	
new: new.o  chkopts
	-${CLINKER} -o new new.o  ${PETSC_TS_LIB}
	${RM} new.o    
    
9bus_dm1: 9bus_dm1.o  chkopts
	-${CLINKER} -o 9bus_dm1 9bus_dm1.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm1.o
	
9bus_dm1_l: 9bus_dm1_l.o  chkopts
	-${CLINKER} -o 9bus_dm1_l 9bus_dm1_l.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm1_l.o
	
9bus_dm1_l2: 9bus_dm1_l2.o  chkopts
	-${CLINKER} -o 9bus_dm1_l2 9bus_dm1_l2.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm1_l2.o

9bus_dm1_l2_new: 9bus_dm1_l2_new.o  chkopts
	-${CLINKER} -o 9bus_dm1_l2_new 9bus_dm1_l2_new.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm1_l2_new.o
       
	
9bus_dm1_fso_new: 9bus_dm1_fso_new.o  chkopts
	-${CLINKER} -o 9bus_dm1_fso_new 9bus_dm1_fso_new.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm1_fso_new.o
    
9bus_dm1_l2_temp: 9bus_dm1_l2_temp.o  chkopts
	-${CLINKER} -o 9bus_dm1_l2_temp 9bus_dm1_l2_temp.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm1_l2_temp.o
	
9bus_dm1_l2_v2: 9bus_dm1_l2_v2.o  chkopts
	-${CLINKER} -o 9bus_dm1_l2_v2 9bus_dm1_l2_v2.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm1_l2_v2.o
	
9bus_dm1_ts: 9bus_dm1_ts.o  chkopts
	-${CLINKER} -o 9bus_dm1_ts 9bus_dm1_ts.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm1_ts.o
	
9bus_dm1_ss: 9bus_dm1_ss.o  chkopts
	-${CLINKER} -o 9bus_dm1_ss 9bus_dm1_ss.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm1_ss.o
	
9bus_dm1_fs: 9bus_dm1_fs.o  chkopts
	-${CLINKER} -o 9bus_dm1_fs 9bus_dm1_fs.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm1_fs.o

9bus_dm1_fso: 9bus_dm1_fso.o  chkopts
	-${CLINKER} -o 9bus_dm1_fso 9bus_dm1_fso.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm1_fso.o

9bus_dm1_fso_new: 9bus_dm1_fso_new.o  chkopts
	-${CLINKER} -o 9bus_dm1_fso_new 9bus_dm1_fso_new.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm1_fso_new.o
    
9bus_dm1_fso1: 9bus_dm1_fso1.o  chkopts
	-${CLINKER} -o 9bus_dm1_fso1 9bus_dm1_fso1.o  ${PETSC_TS_LIB}
	${RM} 9bus_dm1_fso1.o
    
ex9bus: ex9bus.o  chkopts
	-${CLINKER} -o ex9bus ex9bus.o  ${PETSC_TS_LIB}
	${RM} ex9bus.o

ex9busadj: ex9busadj.o  chkopts
	-${CLINKER} -o ex9busadj ex9busadj.o  ${PETSC_TS_LIB}
	${RM} ex9busadj.o

ex9busopt: ex9busopt.o  chkopts
	-${CLINKER} -o ex9busopt ex9busopt.o  ${PETSC_LIB}

ex9busopt_fd: ex9busopt_fd.o  chkopts
	-${CLINKER} -o ex9busopt_fd ex9busopt_fd.o  ${PETSC_LIB}

runex9bus:
	-@${MPIEXEC} -n 1 ./ex9bus

runex9busadj:
	-@${MPIEXEC} -n 1 ./ex9busadj -viewer_binary_skip_info > ex9busadj_1.tmp 2>&1;	  \
	   ${DIFF} output/ex9busadj_1.out ex9busadj_1.tmp || printf "${PWD}\nPossible problem with ex9busadj_1, diffs above\n=========================================\n"; \
	   ${RM} -f ex9busadj_1.tmp

runex9busopt:
	-@${MPIEXEC} -n 1 ./ex9busopt -viewer_binary_skip_info -tao_monitor -tao_gttol .2 > ex9busopt_1.tmp 2>&1;	  \
	   ${DIFF} output/ex9busopt_1.out ex9busopt_1.tmp || printf "${PWD}\nPossible problem with ex9busopt_1, diffs above\n=========================================\n"; \
	   ${RM} -f ex9busopt_1.tmp

runex9busopt_fd:
	-@${MPIEXEC} -n 1 ./ex9busopt_fd -viewer_binary_skip_info -tao_monitor -tao_gttol .2 > ex9busopt_fd_1.tmp 2>&1;	  \
	   ${DIFF} output/ex9busopt_fd_1.out ex9busopt_fd_1.tmp || printf "${PWD}\nPossible problem with ex9busopt_fd_1, diffs above\n=========================================\n"; \
	   ${RM} -f ex9busopt_fd_1.tmp

clean_files:
	${RM} ex9busopt.o
	-@${RM} ex9bus-SA-*

TESTEXAMPLES_DOUBLEINT32 = ex9bus.PETSc runex9bus ex9bus.rm ex9busadj.PETSc runex9busadj ex9busadj.rm ex9busopt.PETSc runex9busopt ex9busopt.rm ex9busopt_fd.PETSc runex9busopt_fd ex9busopt_fd.rm

include ${PETSC_DIR}/lib/petsc/conf/test
