

# Awesome AWS Pentesting Resources


| S.N | Name                                     | URL                                                                                                                                  |
| --- | ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| 1   | PayloadsAllTheThings - AWS Pentest Guide | [GitHub](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Cloud%20-%20AWS%20Pentest.md) |
| 2   | AWS Pentesting                           | https://cloud.hacktricks.xyz/pentesting-cloud/aws-security                                                                           |
 



# AWS Security Checklist

## Information Gathering

1. **Asset Discovery**
   - Use AWS CLI to list AWS resources:
     ```
     aws ec2 describe-instances
     aws rds describe-db-instances
     ```

2. **DNS Enumeration**
   - Use `dig` or `nslookup` to enumerate DNS records:
     ```
     dig example.com
     nslookup example.com
     ```

## Cloud Service Assessment

3. **Identity and Access Management (IAM)**
   - Review IAM policies and roles using AWS Management Console or AWS CLI:
     ```
     aws iam list-policies
     aws iam list-roles
     ```

4. **Virtual Private Cloud (VPC)**
   - Assess VPC configurations and subnets:
     ```
     aws ec2 describe-vpcs
     aws ec2 describe-subnets
     ```

5. **S3 Bucket Security**
   - Review S3 bucket permissions:
     ```
     aws s3 ls
     aws s3api get-bucket-acl --bucket BUCKET_NAME
     ```

6. **EC2 Instance Security**
   - Assess EC2 instance configurations and security groups:
     ```
     aws ec2 describe-instances
     aws ec2 describe-security-groups
     ```

---
---

# AWS OFFENSIVE SECURITY CHECKLIST

## Information Gathering

1. **Asset Discovery**
   - Identify and enumerate AWS resources.
   - **Tools:** AWS Management Console, AWS CLI, AWS Asset Inventory

2. **DNS Enumeration**
   - Enumerate DNS records for AWS-related domains.
   - **Tools:** `dig`, `nslookup`

## Cloud Service Assessment

3. **Identity and Access Management (IAM)**
   - Review IAM policies and roles.
   - Check for over-permissive permissions.
   - **Tools:** AWS Management Console, AWS CLI, IAM Access Analyzer

4. **Virtual Private Cloud (VPC)**
   - Assess VPC configurations, subnets, and security groups.
   - Check for exposed external IPs and unprotected services.
   - **Tools:** AWS Management Console, AWS CLI, VPC Flow Logs

5. **S3 Bucket Security**
   - Review S3 bucket permissions and access policies.
   - Identify publicly accessible buckets.
   - Test for data leakage vulnerabilities.
   - **Tools:** AWS Management Console, AWS CLI, S3 Bucket Scanner

6. **EC2 Instance Security**
   - Assess EC2 instance configurations and security groups.
   - Identify exposed ports and insecure instances.
   - Check for unpatched software.
   - **Tools:** AWS Management Console, AWS CLI, `nmap` (if applicable)

## Vulnerability Assessment

7. **Automated Scanning**
   - Use AWS Inspector or third-party tools for vulnerability scanning.
   - Identify AWS-specific vulnerabilities.
   - **Tools:** AWS Inspector, Third-party Scanners

8. **Manual Vulnerability Testing**
   - Conduct manual testing for complex vulnerabilities.
   - Test for authentication bypass, API vulnerabilities, and misconfigurations.
   - **Tools:** Manual Testing Frameworks, Burp Suite (if applicable)

## Exploitation and Post-Exploitation

9. **Exploitation**
   - Attempt to exploit identified vulnerabilities.
   - Exercise caution and perform exploitation with proper authorization.
   - **Tools:** Exploitation Tools, Metasploit (if applicable)

10. **Privilege Escalation**
    - Test for privilege escalation within AWS environments.
    - Check for overprivileged IAM roles or EC2 instances.
    - **Tools:** AWS CLI, Manual Techniques

11. **Data Exfiltration**
    - Attempt data exfiltration from AWS resources.
    - Identify sensitive data exposure risks.
    - Test for data transfer controls.
    - **Tools:** Custom Scripts, AWS CLI, AWS DataSync
