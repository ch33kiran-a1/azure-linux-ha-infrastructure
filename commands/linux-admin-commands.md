# Linux Administration Commands

## Service Management

Check service status:

```bash
sudo systemctl status nginx
```

Restart service:

```bash
sudo systemctl restart nginx
```

Enable service at boot:

```bash
sudo systemctl enable nginx
```

---

## Log Investigation

View system logs:

```bash
sudo journalctl -xe
```

View Nginx logs:

```bash
sudo journalctl -u nginx
```

Monitor logs in real time:

```bash
sudo tail -f /var/log/syslog
```

---

## Disk Management

Check disk utilization:

```bash
df -h
```

Check directory sizes:

```bash
du -sh /*
```

Identify large files:

```bash
find / -type f -size +500M
```

---

## CPU & Memory Monitoring

View running processes:

```bash
top
```

Detailed process listing:

```bash
ps -ef
```

Check memory utilization:

```bash
free -m
```

---

## Network Troubleshooting

Check listening ports:

```bash
ss -tulnp
```

Check connectivity:

```bash
ping google.com
```

Validate DNS resolution:

```bash
dig azure.kirantechlab.online
```

Check HTTP response:

```bash
curl -I https://azure.kirantechlab.online
```

---

## SSH Troubleshooting

Validate SSH configuration:

```bash
sudo sshd -T
```

Restart SSH service:

```bash
sudo systemctl restart ssh
```

Check SSH logs:

```bash
sudo journalctl -u ssh
```

---

## File Permissions

Change ownership:

```bash
sudo chown user:user file
```

Modify permissions:

```bash
chmod 755 file
```

Switch user:

```bash
su - username
```
