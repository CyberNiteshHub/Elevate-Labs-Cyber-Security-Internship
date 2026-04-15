# Task 3: Vulnerability Scan Report

## Objective
To identify vulnerabilities in the local system using OpenVAS.

## Tool Used
OpenVAS (Greenbone Vulnerability Manager)

## Target
Local system (127.0.0.1)

## Scan Type
Full and Fast Scan

## Findings

The scan identified multiple vulnerabilities in the system:

1. High Severity Vulnerabilities:
- MySQL outdated version detected
- PostgreSQL outdated version detected
- UnrealIRCd vulnerable version detected

2. Medium Severity Vulnerabilities:
- Samba service vulnerabilities detected

## Risk

- High severity vulnerabilities can allow attackers to gain unauthorized access
- Outdated software can be exploited using known vulnerabilities

## Recommendations

- Update all outdated software packages
- Apply security patches regularly
- Disable unnecessary services
- Use firewall protection

## Conclusion

The vulnerability scan successfully identified multiple high and medium risk issues in the system. Proper mitigation steps should be taken to improve system security.
