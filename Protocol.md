# Messages #

## PUSH ##

PUSH PROGRAM
  * Message from the server to tell a client to install a program

PUSH CONFIG
  * Message from the server to setup or configure a program on the client

PUSH DATA
  * Message from the server that initiates a data transfer

PUSH UPDATE
  * Message from the server that allows the client to update a program or the operating system

PUSH DELETE
  * Message from the server that will tell the client to delete a local resource

PUSH KILL
  * Message from the server that will kill a process or set of processes

PUSH START
  * Message from the server to the client to start a fuzzing or analysis sequence

PUSH CMD
  * Message from the server to the client to execute a command

PUSH RESPONSE
  * Message from the client to the server acknowledging the request and responding with a status code (eg., Success, Error, Acknowledge-Continue)

## QUERY ##

QUERY STATUS
  * Message from the server asking for the status of running fuzzing operations

QUERY RESOURCES
  * Message from the server asking for a resource count (memory, cpu usage, etc) on the client

QUERY SETUP
  * Message from the server asking what applications, configurations and data are installed on the client

QUERY PROGRESS
  * Message from the server to the client asking about information on a particular job

QUERY RESPONSE
  * Message from the client to the server responding with a status code (eg., Sucess, Error, Acknowledge-Continue)

## REPORT ##

REPORT CRASH
  * Message from the client telling the server that an application being fuzzed crashed. The message will also detail information about the crash

REPORT PROGRESS
  * Message from the client telling the server the progress of fuzzing

REPORT READY
  * Message from the client telling the server that it is up and ready to fuzz. This will be the first message sent to the server.

REPORT ERROR
  * Message from the client reporting an error condition

REPORT RESPONSE
  * Message from the server to the client responding with a status (Success, Error, Acknowledge, Acknowledge-Continue)

# Synchronization #
  * Protocol will be asynchronous. <br>
<ul><li>Messages will be transferred over TCP connection. <br>
</li><li>Control Plane Messages shall be transferred over TCP port 12456. Data shall be transferred over port 22 using the SFTP protocol outlined by its respective IETF specification ( <a href='http://tools.ietf.org/html/draft-ietf-secsh-filexfer-13'>http://tools.ietf.org/html/draft-ietf-secsh-filexfer-13</a> ). <br>
</li><li>Messages should be transferred over an encrypted tunnel from and to a client and a server. Encrypted traffic shall adhere to the IPMEIR Specification ( <a href='http://www.nsa.gov/ia/_files/IPMEIR_IS100Core_pdfR1.pdf'>http://www.nsa.gov/ia/_files/IPMEIR_IS100Core_pdfR1.pdf</a> ). <br>
</li><li>Encrypted traffic can be transferred in transport or tunnel mode. <br>
</li><li>Messages will typically exhibit a REQUEST RESPONSE behaviour. <br>
</li><li>The DFUZZ header shall be present in all control plain traffic (ie., messages over port 12456) <br>
</li><li>The Dfuzz control plane traffic (ie., traffic over tcp port 12456) will be a binary protocol. The protocol will be a length specified protocol. <br>
</li><li>Client to client interaction is a potential feature that will be explored in later releases of Dfuzz. <br>
</li><li>Server to server interaction is a potential feature that will be explored in later releases of Dfuzz. <br></li></ul>



<h1>DFUZZ Header Format</h1>
<table><thead><th> <b>Field</b></th><th> <b>Length</b></th><th> <b>Value</b></th></thead><tbody>
<tr><td> DFUZZ Header Identification Number </td><td> 4 bytes </td><td> AAAA (hex) </td></tr>
<tr><td> Message Type </td><td> 4 bytes </td><td> Integer (See "Message Type" section for more details) </td></tr>
<tr><td> Next Header </td><td> 4 bytes </td><td> Integer </td></tr>
<tr><td> Length </td><td> 8 bytes </td><td> Length of header+data </td></tr>
<tr><td> Identification </td><td> 16 bytes </td><td> Integer </td></tr>
<tr><td> Protocol Version </td><td> 2 bytes </td><td> 1 (Integer) </td></tr>
<tr><td> Message ID </td><td> 12 bytes </td><td> Increases per message transaction (ie., Request Response or Request, Ack, Response (Integer) </td></tr>
<tr><td> Padding </td><td> 4 bytes </td><td> Zeros </td></tr>
<tr><td> Data </td><td> Variable </td><td> Additional headers and their appropriate data </td></tr></tbody></table>

<h1>REPORT READY</h1>
<table><thead><th> <b>Field</b></th><th> <b>Length</b></th><th> <b>Value</b></th></thead><tbody>
<tr><td> Next Header </td><td> 4 bytes </td><td> Integer </td></tr>
<tr><td> Length </td><td> 8 bytes </td><td> Integer </td></tr>
<tr><td> First Time </td><td> 1 byte </td><td> 1 (Clients first time joining network), <br> 2 (Client has finished Job(s) and is ready for more tasking), <br> 3 (Client has recovered from an error and is ready for tasking). (Integer) </td></tr></tbody></table>


<h1>PUSH START Header Format</h1>
<table><thead><th> <b>Field</b></th><th> <b>Length</b></th><th> <b>Value</b></th></thead><tbody>
<tr><td> Next Header </td><td> 4 bytes </td><td> Integer </td></tr>
<tr><td> Length </td><td> 8 bytes </td><td> Integer </td></tr>
<tr><td> Job ID </td><td> 8 bytes </td><td> Integer </td></tr>
<tr><td> Program Name </td><td> 8 bytes </td><td> Ascii </td></tr>
<tr><td> Users </td><td> 4 bytes </td><td>  Number of users (Integer)</td></tr>
<tr><td> Username </td><td> 4 bytes </td><td> This field will be repeated for each additional user (Ascii) </td></tr></tbody></table>

<h1>REPORT CRASH Header Format</h1>
<table><thead><th> <b>Field</b></th><th> <b>Length</b></th><th> <b>Value</b></th></thead><tbody>
<tr><td> Next Header </td><td> 4 bytes </td><td> Integer </td></tr>
<tr><td> Length </td><td> 8 bytes </td><td> Integer </td></tr>
<tr><td> Job ID </td><td> 8 bytes </td><td> Integer </td></tr>
<tr><td> Unique Crash Identifier Type </td><td> 2 bytes </td><td> Number representing the unique crash identification method. <br> This field will be repeated for each crash identifier type and its subsequent crash hash. <br> Crash Identification type implies encoding and hashing algorithm (Integer) </td></tr>
<tr><td> Unique Crash Hash </td><td> 32 bytes </td><td> Unique hash (Hex) </td></tr>
<tr><td> Full Path To File </td><td> 12 bytes </td><td> Path to file that caused crash (Ascii) </td></tr>
<tr><td> Full Path To Original File </td><td> 12 bytes </td><td> OPTIONAL FIELD. Original non mutated file or packet that was used to generate the crash. (Ascii) </td></tr></tbody></table>

<h1>REPORT RESPONSE Header Format</h1>
<table><thead><th> <b>Field</b></th><th> <b>Length</b></th><th> <b>Value</b></th></thead><tbody>
<tr><td> Next Header </td><td> 4 bytes </td><td> Integer </td></tr>
<tr><td> Length </td><td> 8 bytes </td><td> Integer </td></tr>
<tr><td> Response Status Code </td><td> 4 bytes </td><td> 1 (Success), 2 (Error), 3 (Acknoledge-Continue) (Integer) </td></tr></tbody></table>

<h1>PUSH CONFIG Header Format</h1>
<table><thead><th> <b>Field</b></th><th> <b>Length</b></th><th> <b>Value</b></th></thead><tbody>
<tr><td> Next Header </td><td> 4 bytes </td><td> Integer </td></tr>
<tr><td> Length </td><td> 8 bytes </td><td> Integer </td></tr>
<tr><td> Configuration Type </td><td> 2 bytes </td><td> 1 (Dfuzz Configuration), 2 (application configuration), 3 (fuzzer configuration). (Integer) </td></tr>
<tr><td> Number of configuration files </td><td> 4 bytes </td><td> Integer </td></tr>
<tr><td> Taget Location For Configuration </td><td> 12 bytes </td><td> Path to where the configuration file will be loaded. <br> This field shall be added for each additional configuration file. (Ascii) </td></tr></tbody></table>


<h1>Message Types</h1>
The Message Type field in the DFUZZ Header is a numerical representation of the type of message sent (ie., PUSH PROGRAM, PUSH CONFIG, QUERY STATUS, REPORT CRASH, etc..). The number/integer corresponding to the particular message is detailed below: <br>

1  PUSH PROGRAM <br>
2  PUSH CONFIG <br>
3  PUSH DATA <br>
4  PUSH UPDATE <br>
5  PUSH DELETE <br>
6  PUSH START <br>
7  PUSH KILL <br>
8  PUSH CMD <br>
9  PUSH RESPONSE <br>
20 QUERY STATUS <br>
21 QUERY RESOURCES <br>
22 QUERY SETUP <br>
23 QUERY PROGRESS <br>
24 QUERY RESPONSE <br>
40 REPORT CRASH <br>
41 REPORT PROGRESS <br>
42 REPORT READY <br>
43 REPORT ERROR <br>
44 REPORT RESPONSE <br>