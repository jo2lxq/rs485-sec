# Data Set for Modbus/RS-485 Industrial Control Network Security Research

![Architecture](architecture.png)

Description 

## DataSet Files
 1. 0101-ct_m-s1_at_s2.csv
 2. 0102-ct_s3-s4_at_s2.csv
 3. 0201-ct_m-s1_at_s2.csv
 4. 0202-ct_s3-s4_at_s2.csv
 5. 0301-ct_m-s1_at_s2.csv
 6. 0302-ct_s3-s4_at_s2.csv
 7. 0401-ct_m-s1_at_s2.csv
 8. 0402-ct_s3-s4_at_s2.csv
 9. 0501-ct_m-s1_at_s2.csv
 10. 0502-ct_s3-s4_at_s2.csv

## File Name Rule
 XXYY-ct_A-B_at_C.csv

 ### XX: Attack Scenario
  01: Spoofing Attack  
  02: Random Collision Attack  
  03: Horizontal Scan Attack  
  04: Vertical Scan Attack  
  05: Evil-Twin Attack  
  
 ## YY: Index Numbers
  01: DataSet 1  (Monitoring near the Client)  
  02: DataSet 2  (Monitoring at the far end)  
  
 ## A-B: CT's connection point, one of {m-s1, s1-s2, s2-s3, s3-s4}
  If DataSet 1, "A-B" is "m-s1".  
  If DataSet 2, "A-B" is "s3-s4".
  
 ## C: Attack point, one of {m, s1, s2, s3, s4}
  If "C"="s2", the attacker is located at Server ID=2

## Data Format

## Explanations of Each Attack Scenario

* DataSet of Spoofing Attack (XX Code: 01)

An attacker transmits jamming signals on the communication line after reading the first four bytes of a request from the Client. Here, the first four bytes contain the Server ID and register address, and the attacker can identify the spoofing target. The jamming signals break the later part of the request frame including the CRC16 checksum area. Then, the legitimate server just considers that it has received a broken message and does nothing. Instead, the attacker transmits its spoofed response message as the legitimate Server.

* DataSet of Random Collision Attack (XX Code: 02)

An attacker transmits jamming signals on the communication line at random when it observes a legitimate signal on the line. This destroys the request frames from the Client, and the communication between the Client and the Server would be denied.

* DataSet of Horizontal Scan Attack (XX Code 03)

An attacker requests Servers on the network by changing the Server ID from ID=01H to 7FH, expecting some form of response, including an error response, from the specified Server if it exists.

* DataSet of Vertical Scan Attack (XX Code 04)

An attacker requests to read from a wider range of register addresses instead of a smaller set of register addresses one by one. The purpose of this attack is to explore data – which are usually not used in system operation and are not exchanged on the communication line but still exist on the Server. 

* DataSet of Evil Twin Attack (XX Code: 05)

An attacker sends requests on behalf of the legitimate Client. The requests are identical to those of the legitimate Client. However, accepting and responding to the attacker’s requests should be avoided, and these kinds of anomalous requests should be detected.

## References

Please cite the first paper (i.e., [1]) when you publish your research with this dataset.

[1] Hideya Ochiai , Md Delwar Hossain, Pawissakan Chirupphapa, Youki Kadobayashi, Hiroshi Esaki, "Modbus/RS-485 Attack Detection on Communication Signals with Machine Learning", (to be announced), 2023.

[2] Pawissakan Chirupphapa, Md Delwar Hossain, Hiroshi Esaki, and Hideya Ochiai, "Unsupervised Anomaly Detection in RS-485 Traffic using Autoencoders with Unobtrusive Measurement", IEEE International Performance, Computing, and Communications Conference (IPCCC), 2022.

[3] Md Delwar Hossain, Hideya Ochiai, Tatsuya Arisawa, Youki Kadobayashi, "Smart Meter RS-485 Spoofing Attack Detection by LSTM Deep Learning Approach", IEEE Swiss Conference on Data Science (SDS), 2022.
