# Crash Analysis Tools #

Flayer ( http://code.google.com/p/flayer/ )

Valgrind ( http://valgrind.org/ )

  * valgrind --xml=yes --xml-file=vcrash.xml --trace-children=yes ./a.out "%n%n%n%n%n%n"

!Exploitable  ( http://msecdbg.codeplex.com/ )

Crashwrangler  ( http://seclists.org/dailydave/2009/q3/11 )

Automated Exploit Generation  ( http://security.ece.cmu.edu/aeg/index.html )

Pmcma  ( http://www.pmcma.org/downloads-2/ )

GDB ( http://wiki.python.org/moin/DebuggingWithGdb )

Bitblaze  ( http://bitblaze.cs.berkeley.edu/ )

Introspector ( http://introspector.sourceforge.net/ )


# Core File analysis #

gdb
```
#get backtrace and redirect to a file
echo "bt" > batchfile; echo "quit" >> batchfile; gdb a.out core.9648 -x batchfile | grep " 0x" > bt.txt  
```

abrt-action-analyze-core (Analysis of libraries that are loaded)
  * abrt-action-analyze-core -c core.1090

abrt-action-generate-backtrace (Uses gdb in batch mode("gdb -b"))

abrt-action-analyze-backtrace

man core (core file names can be changed)

lldb ( http://lldb.llvm.org/ )

strings (look for strings in the core file where the mutated pdf files are located)
```
strings -n 10 core.11203 | grep "fuzzing_applications/filep/out" | grep pdf | head -1
/home/username/workspace/dfuzz/trunk/fuzzing_applications/filep/out/sample-2.pdf
```