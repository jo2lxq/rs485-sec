# Data Set for Modbus/RS-485 Industrial Control Network Security Research

![Architecture](architecture.png,"Architecture")

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

## DataSet Format



## Explanations of Each Attack Scenario


* DataSet of Spoofing Attack (XX Code: 01)

  Spoofing happens when an attacker reads the first 4 request bytes and makes a collision, and replies a spoofed message on behalf of the true slave.  This dataset contains the observation of the request frames.

* DataSet of Simple Random Collision Attack (XX Code: 02)

  Collision Attack happens when an attacker overrides the frame sent by someone.

* DataSet of Horizontal Scan Attack (XX Code 03)

  Horizontal Scan happens when an attacker accesses wide-range of the devices in a network. 

* DataSet of Vertical Scan Attack (XX Code 04)

  Vertical Scan happens when an attacker accesses wide-range of the registers of a device.

* DataSet of Evil Twin Attack (XX Code: 05)

  Evil Twin happens when an attacker sends a request, and overrides the previous request.

## Cite the following paper

*
