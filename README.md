# Analyze Network Layer Communication

## Scenario

You are a cybersecurity analyst working at a company that specializes in providing IT services for clients. Several customers of clients reported that they were not able to access the client company website www.yummyrecipesforme.com, and saw the error “destination port unreachable” after waiting for the page to load. 

You are tasked with analyzing the situation and determining which network protocol was affected during this incident. To start, you attempt to visit the website and you also receive the error “destination port unreachable.” To troubleshoot the issue, you load your network analyzer tool, tcpdump, and attempt to load the webpage again. To load the webpage, your browser sends a query to a DNS server via the UDP protocol to retrieve the IP address for the website's domain name; this is part of the DNS protocol. Your browser then uses this IP address as the destination IP for sending an HTTPS request to the web server to display the webpage  The analyzer shows that when you send UDP packets to the DNS server, you receive ICMP packets containing the error message: “udp port 53 unreachable.”

![image](https://github.com/user-attachments/assets/5db75697-0580-4bed-9a80-7dc30021f8fb)

Now that you have captured data packets using a network analyzer tool, it is your job to identify which network protocol and service were impacted by this incident. Then, you will need to write a follow-up report. 

## Objective

To analyze DNS and ICMP traffic using data from a network protocol analyzer tool (tcpdump) to determine which network protocol was impacted during a cybersecurity incident. This involves inspecting network traffic, identifying the cause of network-related issues, interpreting error messages in the tcpdump log, and proposing a solution to resolve the issue.

### Skills Learned

- Network traffic analysis
- Troubleshooting network issues
- Interpreting log data

### Tools Used

- tcpdump log
- Word processing software for document creation

## Steps

### Step 1: Analyze the tcpdump Log

#### 1.1 Initial Requests

The first two lines show that my computer sent a request to a DNS server to get the IP address for the website "yummyrecipesforme.com." This request used the UDP protocol.

![350328219-5db75697-0580-4bed-9a80-7dc30021f8fb (1)](https://github.com/user-attachments/assets/acf7331d-1eca-4d25-a399-b60c822576cf)
> *Ref 1: Outgoing UDP request from my computer to the DNS server.*

#### 1.2 Error Responses

Instead of getting the IP address, the server sent back an error message saying "udp port 53 unreachable." This means the DNS server couldn't process the request because the port it uses (port 53) wasn't available.

![350328219-5db75697-0580-4bed-9a80-7dc30021f8fb (2)](https://github.com/user-attachments/assets/0e3d7024-fab7-4741-9092-c1a3edccf9be)
> *Ref 2: ICMP error message.*

#### 1.3 Timestamps and Addresses

Each log entry contains a time stamp, showing exactly when the request and error happened.

![350328219-5db75697-0580-4bed-9a80-7dc30021f8fb (3)](https://github.com/user-attachments/assets/fa0a6d4a-6925-451d-bdc6-cde07ae4cfdf) 
> *Ref 3: The event happened at 1:24 p.m. and 32 seconds into the minute.*

It also shows the source and destination IP addresses.

![350328219-5db75697-0580-4bed-9a80-7dc30021f8fb (4)](https://github.com/user-attachments/assets/93b3a381-c208-4d6e-be30-891734253d93)
> *Ref 4: The source is 192.51.100.15.52444. The destination is 203.0.113.2.*

#### 1.4 Error Details

Two additional connection attempts were made that resulted in the same error, confirming that the issue persisted.

![350328219-5db75697-0580-4bed-9a80-7dc30021f8fb (6)](https://github.com/user-attachments/assets/ed056db2-cdbf-4fd7-a6e3-91c9a7158fb5)
> *Ref 5: Second attempt made at 1:26 p.m.*

![350328219-5db75697-0580-4bed-9a80-7dc30021f8fb (7)](https://github.com/user-attachments/assets/9cb5434e-b311-4c9a-b390-b275f82577b2)
> *Ref 6: Third attempt made at 1:28 p.m.*

### Step 2: Write the Cybersecurity Incident Report

The report below documents the tcpdump log problem and an explanation of my analysis, alongside a possible cause of the incident.

> [!IMPORTANT]
> [Cybersecurity Incident Report: Network Traffic Analysis](https://docs.google.com/viewer?url=https://github.com/user-attachments/files/16317003/Cybersecurity.Incident.Report_.Network.Traffic.Analysis.docx)
