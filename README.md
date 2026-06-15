# Fortinet Enterprise Infrastructure — Containerlab

A fully automated, zero-touch Fortinet enterprise network lab using [containerlab](https://containerlab.dev/). Deploys a 3-tier HA topology with network segmentation, a full monitoring stack, and a traffic-generation client — entirely from code.

## Architecture

**VLANs**

| VLAN | Name | Purpose |
|------|------|---------|
| 10 | MGMT | Out-of-band management |
| 20 | PROD | Production traffic |
| 30 | MON | Monitoring / telemetry |

## Prerequisites

- Docker with root/sudo access
- [containerlab](https://containerlab.dev/install/) (`bash -c "$(curl -sL https://get.containerlab.dev)"`)
- Ansible (`pip install ansible ansible-lint`)
- Fortinet VM images built via [vrnetlab](https://github.com/srl-labs/vrnetlab) (see [Image Build](#image-build))

## Image Build

Fortinet devices run as QEMU VMs inside Docker containers using vrnetlab. Each appliance type requires its own image built from Fortinet's `.qcow2` files.

```bash
git clone https://github.com/srl-labs/vrnetlab
cd vrnetlab/<device-dir>

# Place the renamed qcow2 here, then:
make
```

| Device | vrnetlab dir | Containerlab kind | Notes |
|--------|-------------|-------------------|-------|
| FortiGate | `fortigate/` | `fortinet_fortigate` | Use v7.0.x — v7.2+ requires license + internet activation |
| FortiAnalyzer | `fortianalyzer/` | `generic_vm` | |
| FortiManager | `fortimanager/` | `generic_vm` | |
| FortiSwitch | L2 bridge | `bridge` / `ovs-bridge` | Managed via FortiLink from FortiGate |

## Quick Start

## Common Commands

## Monitoring Stack

| Tool | Role |
|------|------|
| Zabbix | SNMP polling, SYSLOG collection, alerting |
| Prometheus | Metrics scraping via exporters |
| Grafana | Dashboards |
| FortiAnalyzer | Fortinet-native log aggregation & reporting |
| NetFlow | Flow telemetry from FortiGate |

## Project Structure

See [CHANGELOG.md](CHANGELOG.md) for release history.

## Reference Documentation
