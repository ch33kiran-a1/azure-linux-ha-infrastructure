# NSG Misconfiguration Troubleshooting

## Scenario

Linux web server deployed in Azure became inaccessible over HTTP and HTTPS after NSG rule modification.

Observed symptoms:
- Website inaccessible from browser
- HTTPS request timeout
- Load balancer backend unhealthy

---

## Initial Validation

Validated VM power state from Azure portal.

Checked web server locally on VM:

```bash
curl localhost
```

Confirmed Nginx service status:

```bash
sudo systemctl status nginx
```

Verified VM network connectivity.

---

## Azure Network Investigation

Reviewed NSG inbound security rules:
- Port 80 rule validation
- Port 443 rule validation
- Rule priority verification
- Source and destination configuration

Validated subnet and NIC association.

Checked Azure Load Balancer backend health status.

---

## Root Cause Identified

NSG inbound rule misconfiguration blocked:
- HTTP traffic on port 80
- HTTPS traffic on port 443

Traffic denied before reaching backend VM.

---

## Resolution

Corrected NSG inbound rules:
- Allowed TCP port 80
- Allowed TCP port 443
- Verified correct priority order

Applied configuration changes from Azure portal.

---

## Validation

Verified:
- Website accessible over HTTPS
- Load balancer backend healthy
- Browser connectivity restored
- SSL certificate functioning correctly
