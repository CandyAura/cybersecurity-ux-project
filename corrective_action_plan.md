Corrective Action Plan
The corrective action plan for the Kali Linux Server at Synth Wave Productions follows
guidance from NIST SP 800-30 (NIST, 2012) and NIST SP 800-39 (NIST, 2011). The main
risks are allowing attackers to load harmful kernel modules, misconfiguring ptrace_scope, and
enabling redirects that could let attackers hijack traffic. To fix these, Synth Wave Productions
will disable kernel modules, set ptrace_scope properly, and turn off IPv4/IPv6 redirects (NIST,
2012). These actions will be completed in 1 to 2 weeks.
  
The company also lacks security tools like Intrusion Detection/Prevention Systems (IDS/IPS)
and anti-malware software. Synth Wave Productions will install these tools within two weeks
(NIST, 2011). Weak file permissions will be corrected in three days, and the Ctrl+Alt+Del
shortcut will be disabled in one day to prevent accidental reboots (NIST, 2012).


1. Kernel Modules Disabled
Risk Level: High
Mitigation: Disable module loading (sysctl kernel.modules_disabled=1), enforce
SELinux/AppArmor.
Plan: 1 week to configure and audit. Resources: System Admin, Security Team.
2. ptrace_scope Misconfiguration
Risk Level: High
Mitigation: Set kernel.yama.ptrace_scope=2, monitor with EDR tools.
Plan: 1-2 days to configure and verify. Resources: System Admin, IT Security.
3. IPv4/IPv6 Redirects Enabled
Risk Level: High
Mitigation: Disable redirects (sysctl net.ipv4.conf.all.accept_redirects=0).
Plan: 1 day to configure. Resources: Network Admin, Security Team.
4. IDS/IPS & Anti-Malware Missing
Risk Level: High
Mitigation: Deploy IDS/IPS (Snort/Suricata) and anti-malware (ClamAV).
Plan: 2 weeks for deployment and testing. Resources: IT Security, System Admin.
5. Weak File Permissions
Risk Level: Medium
Mitigation: Correct file permissions on sensitive files, use file integrity monitoring tools
(AIDE).
Plan: 3 days for review and updates. Resources: System Admin, IT Security.
6. Ctrl+Alt+Del Enabled
Risk Level: Low
Mitigation: Disable Ctrl+Alt+Del (systemd CtrlAltDelBurstAction=none).
Plan: 1 day for configuration. Resources: System Admin.
