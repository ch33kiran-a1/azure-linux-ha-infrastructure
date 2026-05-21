# Nginx Service Outage Troubleshooting

## Scenario

Website hosted on Azure Linux VM became inaccessible.

Observed symptoms:
- Website not loading
- HTTPS request failure
- Load balancer backend health issues

---

## Initial Validation

Validated website response:

```bash
curl -I https://azure.kirantechlab.online
```

Checked backend VM accessibility.

Verified Azure Load Balancer health probe status.

---

## Linux-Level Investigation

Checked Nginx service status:

```bash
sudo systemctl status nginx
```

Reviewed recent logs:

```bash
sudo journalctl -u nginx
```

Validated port listening status:

```bash
sudo ss -tulnp | grep nginx
```

Tested Nginx configuration syntax:

```bash
sudo nginx -t
```

---

## Root Cause Identified

Nginx service failure caused by:
- Invalid configuration change
- Service stopped unexpectedly
- Port conflict validation

---

## Resolution

Corrected configuration issue and restarted service:

```bash
sudo systemctl restart nginx
```

Enabled automatic startup:

```bash
sudo systemctl enable nginx
```

---

## Validation

Verified:
- Nginx service running
- HTTPS accessibility restored
- Load balancer traffic routing functioning correctly
- Website accessible from browser
