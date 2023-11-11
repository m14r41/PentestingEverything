# Mobile Forensic Checklist

## Pre-Investigation

- [ ] Establish a controlled and secure forensic environment.
- [ ] Document the case background, scope, and objectives.
- [ ] Ensure all forensic tools are up-to-date and compatible with the mobile OS being examined.
- [ ] Verify that all necessary legal permissions and authorizations are in place.

## Device Acquisition

- [ ] Safely power off the mobile device to preserve its state.
- [ ] Use a write-blocker or equivalent device to prevent any write actions to the device.
- [ ] Create a forensic image (logical or physical) of the mobile device.
  - **Tools:** [Cellebrite UFED](https://www.cellebrite.com/), [XRY](https://www.msab.com/products/xry/)
- [ ] Verify the integrity of the acquired image using checksums (e.g., MD5, SHA256).

## Examination of Evidence

- [ ] Analyze the file system structure to identify relevant files and directories.
- [ ] Examine system logs and artifacts for evidence of user activities.
- [ ] Retrieve call logs, SMS/MMS messages, and contacts.
- [ ] Check for installed applications and their associated data.
- [ ] Examine browser history, cache, and cookies.
- [ ] Extract geolocation data and Wi-Fi connection history.
- [ ] Recover deleted files and artifacts, if necessary.
  - **Tools:** [Autopsy](https://www.sleuthkit.org/autopsy/), [Recuva](https://www.ccleaner.com/recuva)
- [ ] Collect information about device settings, accounts, and connected networks.

## Timeline Analysis

- [ ] Create a timeline of events and activities on the mobile device.
- [ ] Correlate events from different sources to establish a chronological sequence.
- [ ] Identify patterns or anomalies in user interactions.

## Messaging App Analysis

- [ ] Extract data from popular messaging apps (WhatsApp, Signal, Telegram, etc.).
- [ ] Analyze chat conversations, attachments, and call logs.
- [ ] Recover deleted messages if possible.
  - **Tools:** App-specific extraction tools, forensic software

## Multimedia Analysis

- [ ] Examine photos, videos, and audio files for evidence.
- [ ] Extract metadata (timestamps, GPS coordinates, camera details).
- [ ] Identify tampering or manipulation of multimedia files.
- [ ] Check for hidden or encrypted files and folders.

## Social Media and Cloud Data

- [ ] Investigate cloud backups and synced data (e.g., iCloud, Google Drive).
- [ ] Access and analyze social media accounts and activities.
- [ ] Examine email accounts and associated communication.

## Data Recovery

- [ ] Use advanced data recovery techniques to retrieve deleted data.
- [ ] Handle encryption and decryption processes for secured data.
- [ ] Ensure data recovery does not alter or damage the original evidence.

## Reporting and Documentation

- [ ] Create a comprehensive forensic report detailing findings, analysis, and conclusions.
- [ ] Document the forensic process, including acquisition, examination, and analysis steps.
- [ ] Include all relevant artifacts, logs, and extracted evidence in the report.
- [ ] Ensure the report is clear, concise, and well-organized.

## Preservation of Evidence

- [ ] Store all forensic evidence securely to prevent tampering or loss.
- [ ] Maintain a record of who has accessed the evidence and for what purpose.
- [ ] Comply with legal and ethical guidelines for evidence preservation.

## Legal Considerations

- [ ] Adhere to legal requirements and obtain necessary permissions for the investigation.
- [ ] Consult with legal counsel if required for handling sensitive cases.

