# mofaal-IntrusionDetection
## Objective

Implement and explore Snort, an open-source network-based intrusion detection system (NIDS), to bolster defensive measures against network-based attacks. This project entails configuring Snort to detect simple traffic patterns such as port scans, using both pre-defined and custom rules.

## Actions Taken

### Setting Up the Environment

- Started Snort in the Windows 2008 VM by running the command `snort –W` to verify proper initialization.

### Configuration with Native Rules Files

- Created a configuration file and ensured the presence of the dos.rules file in the designated directories.
- Ran Snort with the specified configuration file and monitored the command console for activity.

### Configuration with Custom-Made Rules Files

- Crafted a custom rules file named xmas.rules and incorporated it into the Snort configuration.
- Modified the configuration file accordingly and re-ran Snort to apply the new rules.

### Logging to Windows Event Log

- Enhanced logging capabilities by adding `-y` and `-E` switches to the Snort command.
- Monitored the Windows event log for Snort-generated events, focusing on those related to Port 139.

