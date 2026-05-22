# SSH Access Failure Troubleshooting

## Scenario

Unable to connect to Azure Linux VM using SSH.

Error observed:

```bash
ssh: connect to host <public-ip> port 22: Connection timed out
```

---

## Initial Checks

Validated VM power state from Azure portal.

Checked NSG inbound rules:
- Port 22 allowed
- Source IP validation
- Priority order verification

Checked VM public IP association.

---

## Linux-Level Validation

Verified SSH service status:

```bash
sudo systemctl status ssh
```

Checked listening ports:

```bash
sudo ss -tulnp | grep 22
```

Validated SSH configuration:

```bash
sudo sshd -T | grep passwordauthentication
```

Reviewed authentication logs:

```bash
sudo journalctl -xe
```

---

## Root Cause Identified

Multiple SSH failure scenarios were simulated and resolved including:
- NSG inbound rule misconfiguration
- Public IP dissociation
- Incorrect SSH authentication settings
- SSH service interruption

---

## Resolution

- Corrected NSG inbound rule
- Re-associated public IP
- Restarted SSH service

```bash
sudo systemctl restart ssh
```

---

## Validation

Validated successful SSH connectivity after fixes.

Verified:
- Remote SSH login
- VM network reachability
- SSH service status
- Web server accessibility
