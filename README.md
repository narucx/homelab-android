# Homelab Control

A native Android app for monitoring and managing a self-hosted homelab. It brings the status of
hypervisors, backups, media services, DNS and monitoring into one place and covers the everyday
actions that would otherwise mean opening a dozen web UIs.

> **Personal project.** The app is built for my own homelab and published as-is. Every service is
> optional and configured in the app, so it works with any setup that runs the same software, but
> there is no support and I don't take feature requests.

## Download

- Latest APK: [homelab.apk](https://github.com/narucx/homelab-android/releases/latest/download/homelab.apk)
- Requires Android 8.0 or newer. The app updates itself from this repository's releases.

This repository holds release builds only.

## Connectors

| Service | What you see | What you can do |
|---|---|---|
| Proxmox VE | Cluster, nodes, storage, guests, usage charts, tasks | Start, stop, restart VMs and containers |
| Proxmox Backup Server | Datastore usage and trend, backup groups, snapshots, task logs | Read-only |
| OPNsense | System, gateways, services, WireGuard, DHCP leases, traffic, firewall log | Firmware check and update, reboot |
| Komodo | Stacks, servers, deployments, containers, logs | Start, stop, restart, deploy, pull, destroy |
| Pterodactyl | Servers, resources, backups, live console | Power actions, console commands, backups |
| Sonarr / Radarr | Library, wanted, queue, history, health (up to two instances each) | Search, interactive grab, monitoring, manual import, queue cleanup |
| Prowlarr | Indexers, stats, history, health | Test, enable/disable, search and grab |
| Jellyseerr | Requests, media details, discover | Approve, decline, retry, request |
| SABnzbd | Queue, history, job files, speed | Pause/resume, speed limit, retry, delete |
| Jellyfin | Server info, active sessions, library counts, users, devices | Read-only |
| Dispatcharr | Channels, streams, EPG, M3U accounts, live connections | Refresh sources, stop streams, switch stream |
| Tracearr | Active streams with quality details, playback history | Read-only |
| Uptime Kuma | Monitors, heartbeats, maintenance, status pages | Pause/resume, edit monitors, post incidents |
| Beszel | Systems, metrics history, containers, alerts | Pause/resume a system |
| Scrutiny | Disks, SMART attributes, temperature history | Read-only |
| PatchMon | Hosts, pending packages, update age | Read-only |
| AdGuard Home | Stats and query log across instances | Toggle protection (also timed), clear cache |
| Technitium DNS | Stats and query log across cluster nodes | Read-only |
| Umami | Websites, visitors, metrics, live visitors | Read-only |
| Grafana / Loki | Web traffic: top hosts, countries, paths, traffic classes | Read-only |
| Graylog | Errors by source, recent error messages, alerts | Read-only |
| Gotify | Messages and applications | Read-only |
| Forgejo | Repositories and latest releases | Read-only |
| Claude Code usage | Token and cost totals, daily heatmap, usage limit status | Read-only |

The Claude Code page reads a JSON file from a small self-hosted aggregator script, since there is no
public usage API for subscriptions. Without that script it stays empty.

## Features

- Dashboard with the health of every connected service, plus a home screen widget and a Quick
  Settings tile
- Background health checks with notifications, quiet hours and per-service muting
- Global search across services
- App lock with biometrics or the device credential
- Credentials stored encrypted on the device; encrypted export and import of the configuration
- Log of every write action taken from the app
- Second-screen support on dual-screen devices
- English and German, light and dark theme

## How it was built

The app was developed together with [Claude Code](https://claude.com/claude-code) and has been
audited by Claude several times (security, reliability, performance, accessibility), with the
findings fixed release by release.
