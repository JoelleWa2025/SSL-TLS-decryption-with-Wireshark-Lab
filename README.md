# SSL-TLS-decryption-with-Wireshark-Lab
                                          PART 1: ENCRYPTED

<img width="975" height="523" alt="image" src="https://github.com/user-attachments/assets/06fb0f08-60bb-4b04-9247-3e26fe55ad5f" />

This capture appears to be a secure loopback capture sending an encrypted message to the server and the server back to the localhost/client.
The first three frames is when the packets start to get sent. The loopback using TCP protocols perform the 3 way-handshake. The first packet gets sent to the server as SYN then there is SYN and acknowledge from the server, finally the server acknowledges the source IP.

TCP Stream

<img width="975" height="524" alt="image" src="https://github.com/user-attachments/assets/2f5b00c1-7bf4-47fd-a89b-8edaf3c92004" />

The red colour denotes client packets. In this case there are 10.
The blue colour denotes server packets. In this case there are 11.
This is an encrypted website. The information that can be gathered is the server’s name i.e. Team1.0, which leads to website called snakeoil. Also, can see the certificate. For the client they perform actions; however, it is encrypted just like the server actions. This cannot be seen because it is using the SSLv2 protocol encryption.

TLS Stream

<img width="714" height="1238" alt="image" src="https://github.com/user-attachments/assets/f8880857-975c-413c-9b24-439afa410bb6" />

The results are null. There are 0 clients and 0 server packets because the data is encrypted. Also, SSL is an older version of TLS. 
The information shown in frame 6 is the use of SSLv3 protocol, Info: Server Hello, Certificate, Server Hello Done. This means that the server is responding to the client by saying Hello while sending a certificate to the client as confirmation. 
Frame 32 is dealing with application data. When the encrypted message was sent to the server. 

                                PART 2: DECRYPTED

Everything is almost the same when it comes to TCP, which is the 3-way handshake, but the HTTP protocol has no encrypted messages being sent and the application data is no longer there.

TCP Stream

<img width="885" height="782" alt="image" src="https://github.com/user-attachments/assets/cf039a0c-9efb-44cd-80cf-7cd665fd050d" />

Nothing has change because it is using the same TCP protocol as before and it the end of the TCP 3 way-handshake.

TLS Stream

<img width="975" height="845" alt="image" src="https://github.com/user-attachments/assets/5f0d24d4-5dbc-4d3e-b0b6-f5af583dbfff" />

A lot has changed. There is information in the TLS stream because it is longer secured/ encrypted because of the Hypertext Protocol. The user can now see all the content that is on the website.
The information given is clearly layout. There is HTML script, the operating system which it was built on Linux, the date which was Mon, 24 April 2006 and time. All the installation information and websites that were used.

                          PART 4: ANAlYSIS

Transport layer security (TLS) is a protocol that secures data that travel over the internet by providing end-to-end encryption (Internet Society, 2024). It is often used to secure internet activity such as web browsing; however, is can also be used for e-mail, file transfers, video/audioconferencing, instant messaging and voice-over-IP (Internet Society, 2024). TLS used to be SSL which is Secure Socket layer (GeeksforGeeks, 2024). In 2015, SSL is no longer a secure form of transporting data (Internet Society, 2024). The importance of the implementation of TLS it to ensure that data is sent over the internet encrypted, as before TLS data was sent unencrypted making it easier for hackers to get information (Internet Society, 2024). 
TLS makes sure that important data such as logins, credit cards and personal information is safe while being sent online (Internet Society, 2024). There are several usages of TLS protocol for example it can encrypted data when while in transit, TLS almost works with all browsers making it capable of exchange information, TLS also provides a range of options when securing data to encryption algorithms and hashing algorithms and lastly TLS is easy to use and to deploy making convenient to secure data when it in transit (GeeksforGeeks, 2024).  TLS function by using an asymmetric cryptography, which is a lager key size making it more complicated to hack with the minimum key length being 1024 bits (Internet Society, 2024). TLS using this because it ensures that data is provided with a secure session key while in transit (Internet Society, 2024). 
 The application layer is the last layer in the OSI model.  The application layer is important for providing effective communication between computer and systems (Kirvan & Froehlich, 2022). The application layer ensures that data is received, can ensure data is authenticated for security purposes, data integrity, privacy in communication and so on (Kirvan & Froehlich, 2022).  Applications need to be transported securely to send and receive encrypted application data (Microsoft Learn, 2023).  The application often using HTTP to allow users to access online web browser such as Google (Microsoft Learn, 2023). 
As per the assignment, before the key was applied the encryption was TLS encrypted in the presentation layer. Meaning that as the user could not see the application information being sent in the packet. For example, in frame 32 the TLS encryption ensured you could not determine that the application was a .png file. However, once the applied session key the captured packets were decrypted showing the HTTP and other information such as all the messages and files.  The application did apply encryption; however, it was SSL, which is the older version to TLS as a result the HTTP protocol was not encrypted. In the application layer, encryption/ TLS can be used in conjunctions with HTTP to create a secure HTTPS protocol.



References
GeeksforGeeks. (2024, May 23). Transport Layer Security (TLS). https://www.geeksforgeeks.org/transport-layer-security-tls/ 
Internet Society. (2024, July 8). What is TLS & How Does It Work?. (2024, July 8). https://www.internetsociety.org/deploy360/tls/basics/ 
Kirvan, P., & Froehlich, A. (2022, March 22). What is the application layer? .TechTarget Networking. https://www.techtarget.com/searchnetworking/definition/Application-layer 
Microsoft Learn. (2023, January 8). Transport layer security protocol. https://learn.microsoft.com/en-us/windows-server/security/tls/transport-layer-security-protocol 

                        
