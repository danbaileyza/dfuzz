| **Tool** | **Language** | **Platform** | **Site** | **Fuzzer Type** | **Description** |
|:---------|:-------------|:-------------|:---------|:----------------|:----------------|
| antiparser | Python       | Linux        | http://antiparser.sourceforge.net/ | Generation      | Written in Python, simple and limited fuzzing framework. |
| Autodafe | N/A          | N/A          | http://autodafe.sourceforge.net/ | N/A             | Can be perceived as a more powerful version of SPIKE. It’s main contribution is the introduction of a UNIX-based debugging agent capable of weighting the possibility of a crash on any given fuzz input. |
| AxMan    | N/A          | N/A          | http://digitaloffense.net/tools/axman/ | N/A             | A web-based ActiveX fuzzing engine written by HD-Moore. |
| Bugger   | N/A          | Linux        | N/A      | N/A             | A Linux in-process fuzzer written by Michal Zalewski. |
| COMRaider | N/A          | Win          | N/A      | N/A             | A Windows GUI fuzzer written by David Zimmer, designed to fuzz COM Object Interfaces. |
| Dfuz     | C            | N/A          | http://code.google.com/p/dfuz/ | N/A             | Written in C, exposes a custom and easy to use scripting language for fuzzer deveopment. |
| DOM-Hanoi | N/A          | N/A          | http://digitaloffense.net/tools/domhanoi/domhanoi.html | N/A             | Written by H D Moore and Aviv Raff, DOM-Hanoi is designed to identify common DHTML implementation flaws by adding/removing DOM elements |
| Evolutionary Fuzzing System | N/A          | N/A          | N/A      | Evolutionary    | A fuzzer which attempts to dynamically learn a protocol using code coverage and other feedback mechanisms. |
| FileH    | Haskell      | N/A          | http://www.isecpartners.com/application-security-tools/file-fuzzers.html | Mutation        | A haskell-based file fuzzer that generates mutated files from a list of source files and feeds them to an external program in batches. |
| FileP    | Python       | N/A          | http://www.isecpartners.com/application-security-tools/file-fuzzers.html | Mutation        | A python-based file fuzzer that generates mutated files from a list of source files and feeds them to an external program in batches. |
| Fuzzled  | Perl         | Linux        | http://www.portcullis-security.com/16.php | Generation      | A Perl based generic fuzzing framework. |
| Fuzzbox  | Python       | Linux        | http://www.isecpartners.com/application-security-tools/fuzzbox.html | Mutation        | Fuzzbox is a multi-codec media fuzzer. |
| General Purpose Fuzzer | C            | N/A          | http://www.gnucitizen.org/blog/general-purpose-fuzzer_py/ | N/A             | Written in C, GPF has a number of modes ranging from simple pure random fuzzing to more complex protocol tokenization. |
| hamachi  | N/A          | N/A          | http://digitaloffense.net/tools/hamachi/hamachi.html | N/A             | Written by H D Moore and Aviv Raff, Hamachi will look for common DHTML implementation flaws by specifying common “bad” values for method arguments and property values. |
| Malybuzz | Python       | Linux        | http://sourceforge.net/projects/malybuzz/ | Generation      | A Python tool focused in discovering programming faults in network software. |
| mangleme | N/A          | N/A          | http://freecode.com/projects/mangleme | N/A             | An automated broken HTML generator and browser tester, originally used to find dozens of security and reliability problems in all major Web browsers. |
| Peach    | Python       | Win          | http://peachfuzzer.com/ | Generation      | Written in Python, an advanced and robust fuzzing framework which successfully separates and abstracts relevant concepts. Learning curve is a bit overwhelming. |
| Protocol Informatics | N/A          | N/A          | http://www.4tphi.net/~awalters/PI/PI.html | N/A             | Slides, whitepaper and code from the last publicly seen snapshot from Marshall Beddoe’s work. |
| QueMod (QueFuzz) | C            | Linux        | https://github.com/struct/QueMod, http://code.google.com/p/quefuzz/ | N/A             | Small fuzzer that uses libnetfilter\_queue to take in packets from iptables. It’s fuzzing engine either randomly fuzzes binary or ASCII protocols or uses a basic fuzzing template to search and replace packet data. |
| Schemer  | N/A          | N/A          | http://www.fuzzware.net/Schemer/Schemer.htm | N/A             | XML driven generic file and protocol fuzzer. |
| SMUDGE   | Python       | N/A          | http://gpo.zugaina.org/app-fuzz/smudge/euscan | N/A             | Pure Python network protocol fuzzer from nd@felincemenace. |
| SPIKE    | N/A          | N/A          | http://immunityinc.com/resources-freesoftware.shtml | N/A             | Written in C, exposes a custom API for fuzzer development. Probably the most widely used and popular framework. |
| TAOF (The Art of Fuzzing) | Python       | Win, Linux   | http://sourceforge.net/projects/taof/ | N/A             | Written in Python, a cross-platform GUI driven network protocol fuzzing environment for both UNIX and Windows systems. |
| Spikefile | C            | Linux        | http://www.fuzzing.org/wp-content/SPIKEfile.tgz | N/A             | N/A             |
| PIF      | N/A          | N/A          | N/A      | N/A             | N/A             |
| htmler   | Python       | Linux, Windows | http://www.securiteam.com/tools/6Z00N1PBFK.html | Mutation        | Python port of mangleme. Works by mutating an HTML file or set of HTML files |
| Sysfuzz  | N/A          | N/A          | http://good.net/dl/bd/www.indianz.ch/tools/attack/sysfuzz.tar.gz | N/A             | N/A             |
| Iknowthis | N/A          | N/A          | http://code.google.com/p/iknowthis/source/browse/http://code.google.com/p/iknowthis/ | N/A             | N/A             |
| Xnufuzz  | C            | Linux        | https://github.com/fintler/xnufuzz | N/A             | Kernel Fuzzer   |
| Bed      | Perl         | Linux, Win   | http://www.aldeid.com/wiki/Bed, http://web.archive.org/web/20101229024258/http://www.remote-exploit.org/wp-content/uploads/2010/01/bed-0.5.tar.gz | Generation      | BED (aka Bruteforce Exploit Detector) is a plain-text protocol fuzzer that checks software for common vulnerabilities like buffer overflows, format string bugs, integer overflows, etc |
| IRCfuzz  | N/A          | N/A          | N/A      | N/A             | N/A             |
| isic     | N/A          | N/A          | N/A      | N/A             | N/A             |
| axfuzz   | N/A          | N/A          | http://sourceforge.net/projects/axfuzz/ | N/A             | An ActiveX/COM enumerator and fuzzer  |
| fuzzserver | N/A          | N/A          | N/A      | N/A             | N/A             |
| stress2  | N/A          | N/A          | http://people.freebsd.org/~pho/stress/index.html | N/A             | linux kernel fuzzer |
| mangle   | N/A          | N/A          | N/A      | N/A             | N/A             |
| capouik  | Python       | N/A          | http://code.google.com/p/capouik/ | Mutation        | Take a pcap as input, fuzz it and replay packets against a host.  |
| sshreader | N/A          | N/A          | N/A      | N/A             |
| sfuzz    | N/A          | N/A          | http://aconole.brad-x.com/programs/sfuzz.html | N/A             | Simple Network Protocol Fuzzer |
| dhcpfuzz | N/A          | N/A          | http://good.net/dl/bd/www.indianz.ch/tools/attack/dhcpfuzz.tar.gz/info | N/A             | N/A             |
| scapy    | Python       | Win, Linux, Mac | http://www.secdev.org/projects/scapy/ | Generation      | Scapy is a powerful interactive packet manipulation program. It is able to forge or decode packets of a wide number of protocols, send them on the wire, capture them, match requests and replies, and much more.  |
| combust  | N/A          | N/A          | N/A      | N/A             | N/A             |
| hot fuzz | N/A          | N/A          | http://hotfuzz.sourceforge.net/ | Generation      | Fuzzer based on the peach framework. Basic protocols are implemented in the Peach framework |
| Dranzer  |  C           | Win          | http://www.cert.org/vuls/discovery/dranzer.html | N/A             | ActiveX Fuzzer built to target Microsoft Internet Explorer |
| Mistress |  Python      | Linux, Win   | http://www.koders.com/python/fidAB461618BA5DFFF2D50E6BEC124C00A8A2F89F8C.aspx?s=socket | Generation      | File and Protocol fuzzer based on templates created by the user.  |
| minifuzz |  C++         | Win          | http://examples.oreilly.de/english_examples/9780735622142/cd_contents/MiniFuzz/ | N/A             | N/A             |
| smartfuzz |  C           | Linux        | https://github.com/dmolnar/SmartFuzz | N/A             | N/A             |
| PROTOS   |  Java        | N/A          | https://www.ee.oulu.fi/research/ouspg/PROTOS_Test-Suite_c07-h2250v4 | N/A             | N/A             |
| KLEE     |  N/A         | Linux        | http://klee.llvm.org/ | N/A             | Symbolic execution framework and requires llvm |
| Buzzfuzz |  N/A         | N/A          | http://people.csail.mit.edu/vganesh/buzzfuzz.html | N/A             | Buzzfuzz is a dynamic taint-based directed whitebox fuzzing tool. |
| Jfuzz    |  N/A         | N/A          | http://people.csail.mit.edu/akiezun/jfuzz/ | N/A             | N/A             |
| zzuf     |  N/A         | N/A          | http://caca.zoy.org/wiki/zzuf | N/A             | N/A             |
| oofuzzer | Perl         | Linux        | http://www.cl.cam.ac.uk/~wmk26/openoffice/ | Mutation        | Open office fuzzer |
| Fuzzdiff | Python       | Linux, Win,  | http://code.google.com/p/fuzzdiff/source/browse/trunk/fuzzdiff | Mutation        | This is a simple tool designed to help out with crash analysis during fuzz testing.  It selectively "un-fuzzes" portions of a fuzzed file that is known to cause a crash, re-launches the targeted application, and sees if it still crashes.  Eventually, this will yield a file that still causes the crash, but contains a minimum set of changes from the original un-fuzzed file. |
| taviso-fuzz | C            | Linux        | http://freecode.com/projects/taviso-fuzz | Mutation        | Random mutation based file fuzzer |
| fuzzgrind | Python, C    | Linux        | http://esec-lab.sogeti.com/pages/Fuzzgrind | Generation      | Generation based fuzzer that uses constraint solving |