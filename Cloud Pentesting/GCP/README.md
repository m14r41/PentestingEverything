# GOOGLE CLOUD PLATFORM (GCP) OFFENSIVE SECURITY CHECKLIST

## Information Gathering

### 1. Asset Discovery
   - Identify and enumerate GCP resources and assets.
   - Utilize GCP-native tools or APIs for asset discovery.
   - **Tools:** Google Cloud Console, Google Cloud SDK, Asset Inventory

### 2. DNS Enumeration
   - Enumerate DNS records for GCP-related domains.
   - Identify public-facing services and subdomains.
   - **Tools:** DNS Enumeration Tools (e.g., **dig**, **nslookup**)

## Cloud Service Assessment

### 3. Identity and Access Management (IAM)
   - Review IAM policies and roles for GCP resources.
   - Identify overly permissive permissions and misconfigurations.
   - **Tools:** Google Cloud Console, **gcloud** command-line tool

### 4. Virtual Private Cloud (VPC)
   - Assess VPC configurations, subnets, and firewall rules.
   - Check for exposed external IPs and unprotected services.
   - **Tools:** Google Cloud Console, **gcloud** command-line tool

### 5. Cloud Storage Security
   - Review Google Cloud Storage (GCS) bucket permissions.
   - Identify publicly accessible storage buckets.
   - Test for data leakage vulnerabilities.
   - **Tools:** Google Cloud Console, **gsutil** command-line tool

### 6. Kubernetes Security
   - Assess Google Kubernetes Engine (GKE) cluster configurations.
   - Check for unsecured dashboards and exposed APIs.
   - Identify privilege escalation opportunities within GKE.
   - **Tools:** Google Kubernetes Engine (GKE) Console, **kubectl** command-line tool

## Vulnerability Assessment

### 7. Automated Scanning
   - Perform automated vulnerability scanning using GCP-native or third-party tools.
   - Identify vulnerabilities specific to GCP services.
   - **Tools:** Google Cloud Security Scanner, Third-party Scanners

### 8. Manual Vulnerability Testing
   - Conduct manual testing to identify complex vulnerabilities.
   - Test for authentication bypass, API vulnerabilities, and misconfigurations.
   - **Tools:** Manual Testing Frameworks, **Burp Suite** (if applicable)

## Exploitation and Post-Exploitation

### 9. Exploitation
   - Attempt to exploit identified vulnerabilities to gain unauthorized access.
   - Exercise caution and perform exploitation with proper authorization.
   - **Tools:** Exploitation Tools, **Metasploit** (if applicable)

### 10. Privilege Escalation
   - Test for privilege escalation within GCP environments.
   - Check for overprivileged service accounts or IAM roles.
   - **Tools:** **gcloud** command-line tool, Manual Techniques

### 11. Data Exfiltration
   - Attempt data exfiltration from GCP resources.
   - Identify sensitive data exposure risks.
   - Test for data transfer controls.
   - **Tools:** Custom Scripts, Cloud Storage Tools

