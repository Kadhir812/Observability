# Observability Setup: Four Important Prerequisites

## 1. VM1 and VM2 network confirmation

- VNet: `vnet-southindia-1`
- Subnet: `snet-southindia-1`
- VM2 private IP: `172.16.0.4`
- Confirm that VM1 uses the same VNet and subnet.

## 2. NSG permission

Confirm that the shared NSG, `FS-TO-DemoS-nsg`, allows VM2 to access VM1 on the approved metrics ports.

The rule should allow only:

- Source: VM2 private IP
- Destination: VM1 private IP
- Protocol: TCP
- Ports: Approved metrics ports

## 3. Windows Administrator access

Confirm local Windows Administrator access on both VMs. This is required to:

- Install Windows Exporter and other observability services.
- Configure Windows services.
- Create Windows Firewall rules.

## 4. Approved metrics ports

Confirm which ports can be used for:

- Windows Exporter on VM1.
- Application `/metrics` endpoints on VM1.
- Prometheus and Grafana access on VM2.

Do not expose metrics ports publicly. First complete the basic working setup, then add security hardening.
