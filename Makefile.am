//Makefile.am 은 configure file을 생성하는 데 필요하다. 
//automake의 input
//Makefile.in 이라는 파일을 생성하는데, 이는 Makefile 생성하는 템플릿이다. 

libdir = @libdir@/filebench

SUBDIRS = workloads cvars

# we depend on this lex & yacc generated file
BUILT_SOURCES = parser_gram.h

bin_PROGRAMS = filebench  //생성되는 실행파일 이름
filebench_SOURCES = eventgen.c fb_avl.c fb_localfs.c \       //실행파일을 컴파일하기 위한 소스
		    fb_random.c fileset.c flowop.c flowop_library.c \
		    gamma_dist.c ipc.c misc.c multi_client_sync.c \
		    parser_gram.y parser_lex.l procflow.c stats.c \
		    threadflow.c utils.c vars.c ioprio.c \
		    eventgen.h  fb_random.h  fileset.h  fsplug.h \
		    ipc.h   multi_client_sync.h  parsertypes.h  stats.h \
		    utils.h config.h fb_avl.h filebench.h flowop.h gamma_dist.h \
		    misc.h procflow.h threadflow.h vars.h ioprio.h flag.h \
		    fbtime.c fbtime.h \
		    fb_cvar.c fb_cvar.h aslr.c aslr.h \
		    cvars/mtwist/mtwist.c cvars/mtwist/mtwist.h

EXTRA_DIST = LICENSE

ACLOCAL_AMFLAGS = -I m4
AM_YFLAGS = -d
#AM_LDFLAGS = 
if GCC_USED
AM_CFLAGS = -Wall -Wno-unknown-pragmas
endif

DEFS = -D_REENTRANT -DYYDEBUG -DYY_NO_INPUT -DFBLIBDIR=\"$(libdir)\" -D_LARGEFILE64_SOURCE -D_GNU_SOURCE
