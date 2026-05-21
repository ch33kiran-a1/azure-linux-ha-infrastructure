# SSH Hardening Configuration

## Objective

Implemented SSH security hardening practices on Linux virtual machines hosted in Microsoft Azure.

---

## Security Configurations Applied

### Disabled Password Authentication

Validated SSH configuration:

```bash
sudo sshd -T | grep passwordauthentication
```

Configured:

```text
PasswordAuthentication no
```

---

### Enabled SSH Key Authentication

Validated public key authentication:

```bash
sudo sshd -T | grep pubkeyauthentication
```

Configured:

```text
PubkeyAuthentication yes
```

---

### Disabled Root Login

Configured SSH daemon settings:

```text
PermitRootLogin no
```

---

## Configuration Files Reviewed

```bash
/etc/ssh/sshd_config
/etc/ssh/sshd_config.d/50-cloud-init.conf
```

---

## SSH Service Validation

Restarted SSH service after configuration changes:

```bash
sudo systemctl restart ssh
```

Verified SSH service status:

```bash
sudo systemctl status ssh
```

---

## Validation Performed

- SSH login using key authentication successful
- Password login blocked successfully
- Root login disabled
- SSH service operational after configuration changes

---

## Security Benefits

- Reduced brute-force attack exposure
- Improved remote access security
- Restricted unauthorized login attempts
- Strengthened Linux VM administrative access
