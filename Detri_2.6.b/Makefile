CC=gcc
AR=ar
C_SRCS= \
./basic/isort.c \
./basic/cb_doprnt.c \
./basic/getarg.c \
./basic/time.c \
./basic/prime.c \
./basic/counter.c \
./basic/qsort.c \
./basic/tokenize.c \
./basic/files.c \
./basic/malloc.c \
./basic/basic.c \
./basic/cb.c \
./basic/uhash.c \
./basic/istaque.c \
./basic/math2.c \
./basic/arg.c \
./lia/stack.c \
./lia/det.c \
./lia/pool.c \
./lia/aux.c \
./lia/chars.c \
./lia/lia.c \
./sos/positive3.c \
./sos/primitive.c \
./sos/lambda3.c \
./sos/lambda4.c \
./sos/lambda5.c \
./sos/smaller.c \
./sos/sos.c \
./sos/in_sphere.c \
./sos/minor.c

DETRI_SRCS=./detri/delaunay.c ./detri/detri.c ./detri/dt.c ./detri/flip.c ./detri/peel.c ./detri/prep.c ./detri/print_dt.c ./detri/search.c ./detri/trist.c

C_OBJS=${C_SRCS:%.c=%.o}
DETRI_OBJS=${DETRI_SRCS:%.c=%.o}

C_FLAGS=-I./basic -I./lia -I./sos -I. -g

STATIC=libs/libsos.a
BIN=bin/detri
HEADERS=basic/basic.h lia/lia.h sos/sos.h

all: ${STATIC} ${BIN}

%.o: %.c
	${CC} -c $< -o $@ ${C_FLAGS}
${STATIC}: ${C_OBJS}
	${AR} -cvq $@ ${C_OBJS}
	@cp ${HEADERS} libs

${BIN}: ${DETRI_OBJS} ${STATIC}
	${CC} -o $@ ${DETRI_OBJS} ${STATIC} -lm

test: ${STATIC} test.c
	${CC} test.c ${STATIC} -o test ${C_FLAGS}

clean:
	@rm -f ${C_OBJS} ${DETRI_OBJS}
	@rm -f libs/* bin/*

