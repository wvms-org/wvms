name: wvms-agent
description: Agent for managing secure VMs with display access
tools:
  - lxd.Client methods for VM operations
  - display detection and forwarding

capabilities:
  - Create strict profile VMs
  - Launch GUI apps with display forwarding
  - Manage LXD instances

security:
  - strict profile with security restrictions
  - display socket forwarding via file push
  - no delegation to LXD