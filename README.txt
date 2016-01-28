      Submitted by:
Name:Rashmi sandilya                 Unity:rsandil ID:200084902 
Name:Purna Mani Kumar Ghantasala     Unity:pghanta ID:200066404 


*********Instruction for Executing Peer to Peer with Centralised Index (P2P-CI) System for downloading RFCs*************

All the deliverables for this project are kept in CSC573_PROJECT_1 folder. The content of this folder is:

1. PeerToPeer - contains the code for project
2. RFC test files - contains the RFC sample files to use for testing(if needed)
NOTE: RFC file name format used is rfcno_rfctitle . Ex- If RFC no is 7331 and title is BFD Management then, RFC file name is 7331_BFD Management .


The code has been implemented in Java and the project folder is named as PeerToPeer:

Inside PeerToPeer/src folder there are two sub-folders:
1. Server (For the CI-server side code)
2. Peers (For peer side code)


****************************** compiling and running the code ***************************************************************************************
First the server needs to be up to listen the peers.

***Server side***

Step 1. (To Compile)Go to directory PeerToPeer and run the command-> javac src/Server/*.java
Ex-
C:\Users\Rashmi\workspace\PeerToPeer>javac src/Server/*.java

Step 2. Go to Src folder -> cd src
Ex- 
C:\Users\Rashmi\workspace\PeerToPeer>cd src

Step 3. (To Run)Run the server using command->java Server.CIServer Server-port
Ex-
C:\Users\Rashmi\workspace\PeerToPeer\src>java Server.CIServer 7734

**Peer side**
NOTE: Below step needs to be followed for all peers joining the system.

Step 1. (To Compile)Go to directory PeerToPeer and run the command-> javac src/Peers/*.java
Ex-
C:\Users\Rashmi\workspace\PeerToPeer>javac src/Peers/*.java

Step2: Go to Src folder -> cd src
Ex- 
C:\Users\Rashmi\workspace\PeerToPeer>cd src

Step 3. (To Run)Run the Peer using command->java Peers.peer server-ip server-port

Ex-
C:\Users\Rashmi\workspace\PeerToPeer\src>java Peers.peer 192.168.1.121 7734

Peer will start running 
Execution 1: It will ask for entering the upload port number on console as user input. Enter the upload port number in the usable port number range(Ex-12345)
Ex-
Enter the upload port number:
12345 //(user input)

Execution 2: It will ask for entering the RFC file path for itself as user input. 
Ex- 
Enter the RFC path for this client:
C:\Users\Rashmi\Desktop\CSC573_PROJECT_1\RFC test files\requestPeer //(user input)

Execution3: The various options appear on screen for user input. Now the peer can perform the action based on options on console as
Options:
1. List all RFCs
2. Lookup for an RFC
3. Download an RFC
4. Leave the system
Enter the option:
1 //user input

Option 1: It will list all the RFC's available with the server in the specified format.
Option 2: 
Execution 1: It will ask for entering the RFC number to lookup.
Ex- 
Enter the RFC number you want to lookup :
7331 //(user input)

Execution 2: It will ask for entering the RFC title to lookup.
Ex- 
Enter the RFC title you want to lookup :
BFD Management //(user input)

NOTE: We need to pass the RFC title also as user input since the peer needs to send lookup request for RFC in specific format specified in problem statement which requires both RFC number and title.
This option will give the list of peers having the RFC looked for.

Option 3: 
Execution 1: It will ask for entering the RFC number to download.
Ex- 
Enter the RFC number you want to download :
7331 //(user input)

Execution 2: It will ask for entering the RFC title to download.
Ex- 
Enter the RFC title you want to download :
BFD Management //(user input)

NOTE: We need to pass the RFC title also as user input since for downloading the RFC, peer first needs to lookup with server and the lookup request needs RFC title as per specified format.
This option will download the RFC from the first available peer by establishing the peer to peer connection. If RFC is not found with any peer, '404 not found' status code is returned. If found the RFC is downloaded in RFC folder of this peer.The new RFC is added to the server as part of this option only. No seperate user input is needed to add the new RFC. Also the RFC file content is displayed on console with specified response format.

Option 4: This option exits the peer from the system and socket is closed. The message "Successfully left the system" appears. RFC list and active peer list at server is updated and server shows the message "socket for peer xyz closed". NOTE: xyz is peer ip.


NOTE: If needed, for test purpose two RFC test folders named "requestPeer" and "downlaodPeer" has been kept in 'RFC test files' folder one for requesting peer and one for download peer(peer which gives the file). However any RFC files/folder can be used with the format for filename used by us i.e rfcno_rfctitle.



















