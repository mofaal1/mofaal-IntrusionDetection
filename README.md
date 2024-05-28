# Intrusion Detection with Snort
## Objective

Implement and explore Snort, an open-source network-based intrusion detection system (NIDS), to bolster defensive measures against network-based attacks. This project entails configuring Snort to detect simple traffic patterns such as port scans, using both pre-defined and custom rules.

### Skills Learned

- **Implementation and Configuration:**  
  Experience gained in setting up and configuring Snort for intrusion detection purposes.

- **Rule-based IDS Concepts:**  
  Understanding developed in rule-based IDS concepts and their practical application within Snort.

- **Alerts and Logs Analysis:**  
  Proficiency acquired in analyzing and interpreting Snort alerts and logs to identify potential security threats.

- **Custom Rule Creation:**  
  Ability developed to customize Snort rules to match specific network security requirements.

- **Network Traffic Analysis:**  
  Familiarity gained with network traffic analysis tools such as Wireshark, enhancing the capability to identify anomalies and potential security breaches.

### Tools Used

- **Snort:**  
  Open-source network intrusion detection system used for monitoring and analyzing network traffic for potential security threats.

- **Nmap:**  
  Network scanning tool used for discovering hosts and services on a computer network, thus aiding in vulnerability assessment and network inventory.

- **Zenmap:**  
  Graphical user interface (GUI) for Nmap, providing an intuitive way to interact with Nmap for network scanning and analysis.

- **Various Analysis Tools:**  
  I employed various analysis tools to interpret Snort alerts and logs effectively, enhancing the understanding of network security threats.


## Steps

#### Step 1: Preparing the System

1. **Opened Command Console:**
   - Ran `snort -W` in the Windows 2008 VM to verify Snort started correctly and noted the interface number.

#### Step 2: Configuring Snort to Use Native Rule Files

1. **Created Configuration File:**
   - Typed configuration settings in Notepad and saved as `<FirstInitial><LastName>.conf` in `C:\Snort\etc`.

2. **Verified Rule File and Ran Snort:**
   - Ensured `dos.rules` was in `C:\Snort\rules`.
   - Ran Snort with `snort -c C:\Snort\etc\<FirstInitial><LastName>.conf -l C:\Snort\log -de -i 1`.
   - Verified Snort started correctly.


3. **Noted Time for Zenmap Scan:**
   - Recorded the time before starting the Zenmap `-sT` scan.

4. **Checked Alert Entries in alert.ids:**
   - Verified entries in `alert.ids` matched the recorded time.

5. **Analyzed ps2log File:**
   - Verified ephemeral ports and the state of the scanned ports in `ps2log`.

#### Step 3: Running and Analyzing Xmas Scan

1. **Ran Xmas Scan:**
   - Created `xmas.rules` and updated the configuration file.
   - Reran Snort with the updated configuration.
   - Ran `nmap -sX -p 135-139 10.1.xx.161` in Zenmap.
   - Verified Snort detected the Xmas scan.
  
2. **Checked Control Bits with Wireshark:**
   - Opened `snort.log` in Wireshark.
   - Verified control bits and ephemeral port used in the Xmas scan.

#### Step 4: Logging to Windows Events

1. **Logged Snort Events:**
   - Modified Snort command to include `-y -E` switches and started Snort.
   - Reran Zenmap Xmas scan.
   - Verified five Snort-generated events in Event Viewer.

  
### Screenshots

- **Snort Command Console:**  
  This screenshot displays the Snort command console, showing the piggy icon in the upper left corner, indicating successful detection.

  ![piggy](https://github.com/Mofaal/mofaal-IntrusionDetection/assets/137732122/a2b98e86-8e5f-4cc8-859d-3bf2fcbb19c4)

  
- **alert.ids File:**  
  This screenshot showcases the alert.ids file, highlighting entries matching the time recorded in Question 4.1.2, confirming the presence of relevant alerts.

  ![alert](https://github.com/Mofaal/mofaal-IntrusionDetection/assets/137732122/db90db77-4749-4596-92d1-00f57fc4560b)

- **ps2log File:**  
  This screenshot displays the ps2log file, presenting the ephemeral ports used by the attacker machine to scan five ports on IP address 10.1.188.161 It confirms two ports as open and three as filtered, corroborating the Nmap scan results.
  
  ![ps2](https://github.com/Mofaal/mofaal-IntrusionDetection/assets/137732122/f773052c-8277-4cef-a94f-ef5ec55238d8)

- **Event Viewer:**  
  This screenshot displays the Event Viewer, showcasing five Snort-generated events as requested in Question 4.3.1, confirming their presence.
  
  ![Picture1](https://github.com/Mofaal/mofaal-IntrusionDetection/assets/137732122/aa2ef243-9670-4b06-b58d-a980479bccb0)

