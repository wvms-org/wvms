# wvms - Secure VM Manager

wvms creates secure, isolated VMs using LXD/LXC with X11 and Wayland display server access.

## Project Overview
- **Goal**: Create secure isolated VMs with GUI app support
- **Approach**: Direct socket management, no LXD delegation
- **Security**: Strict profile with display forwarding

## Architecture
- `cmd/create.go`: VM creation with strict profile
- `cmd/launch.go`: Display socket forwarding
- `pkg/lxd/lxd.go`: LXD client wrapper
- `pkg/display/display.go`: X11/Wayland detection

## Security Model
```
security.nesting: false
security.privileged: false  
security.protocols: clear
linux.kernel_modules: ""
```

## Display Forwarding
1. Detect host display (Wayland or X11)
2. Push socket to VM
3. Set environment variables
4. Execute GUI app in VM

## Testing
```bash
go test ./...
go build ./...
go vet ./...
```

## CI/CD
- GitHub Actions for build and test
- Release workflow for versioning