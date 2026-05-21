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

SSH access failure caused by:
- NSG rule misconfiguration
- Public IP removal
- Incorrect SSH authentication settings

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

SSH access restored successfully.

Verified:
- SSH login
- VM network connectivity
- Web server accessibility
