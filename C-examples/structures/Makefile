
#---------------------------------------------------------------
# Using this Makefile
#
#   To compile your C source and produce the executable for
#   all files listed in this Makefile
#
#   make
#
#   To compile and link only one file, e.g. hello, use
#
#	make  hello
#
#   To clean up your directory (e.g. before submission)
#
#   make clean
#
#---------------------------------------------------------------



# The following are macros: a defintion on one line with an equal 
# to sign. The CC macro is used to define the C compiler and the 
# macro CFLAGS defines the default set of options or flags used 
# with the C compiler.
CC=gcc
CFLAGS=-Wall -g

# Recognize files with .c and .o extensions
.SUFFIXES: .o .c

# This is a rule to convert a file with .c extension
# into a file with a .o extension. The macro $< just
# supplies the name of the file (without the extension)
# that invoked this rule.
.c.o: 
	$(CC) $(CFLAGS) -c $<

# The following is a dependency or a rule line. It has the
# name of the rule followed by a colon. After the colon are listed
# other rules that this rule depends upon. Following the rules line 
# are one or more command lines that must start with a TAB character.
all: structs-ex0 point-test 

# Another rule below. This depends upon the rule hello.o but we don't
# have any such rule. However make recognizes the suffix .o and uses
# the .c.o rule above to locate the hello.c file and builds the hello.o
# using the .c.o rule.
structs-ex0: structs-ex0.o
	$(CC) $(CFLAGS) $< -o $@

point-test: point.o point-test.o
	$(CC) $(CFLAGS) $^ -o $@

# A rule most that all Makefiles should have. This one removes
# any .o files and other undesirables that are  lying around and 
# the executable hello and leaves only the source. Useful for running 
# before submitting a program!
clean:
	/bin/rm -f *.o point-test structs-ex0 
