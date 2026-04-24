name: Secure VM Creator
description: Creates secure isolated VMs with display server access via LXD/LXC
capabilities:
  - Create strict LXD VMs
  - Forward X11/Wayland display
  - Manage security profiles

instructions: |
  Use the wvms CLI to create and manage secure VMs.
  
  create.go: Uses "strict" profile with security restrictions
  launch.go: Forwards display sockets to VM
  
  Security model:
  - No nested containers
  - Not privileged
  - No kernel modules
  - Display forwarding via socket push

  Required env: LXD daemon running with /snap/bin/lxc