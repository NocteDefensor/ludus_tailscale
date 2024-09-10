# ludus_tailscale
Ansible Role for Ludus to provision or remove a device to/from a Tailnet.

## Installation Instructions
- Clone this repo
```
git clone https://github.com/NocteDefensor/ludus_tailscale.git
```
- add it to ludus roles
```
ludus ansible role add -d ./ludus_tailscale
```
- set your config like the one in the example ludus-config.yaml
  - Ensure your api key is for a user with permissions to remove devices from the tailnet.
  - ensure auth key is valid
- either deploy whole range with
```
ludus range deploy
```
- or deploy just tailscale role
  - Useful for deploying tailscale to existing vm's or removing tailscale from existing VM's.
  - **Hint**: can be used with "absent" as the tailscale state variable value to purge tailscale prior to destroying range.
```
ludus range deploy -t user-defined-roles --only-roles ludus_tailscale
```
