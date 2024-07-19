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

### Step 1: 
