# ludus_tailscale
Ansible Role for Ludus to provision or remove a device to/from a Tailnet.
## REQUIREMENTS
- Requires Ludus 1.5.4 or greater as this version and above contain improvements in IP determination within the Dynamic Inventory steps which affect how Ludus operates in a Tailscale environment.
- Tailscale authorization key which is configured for reuse if going to be used for more then one VM.
- Tailscale API key with permissions to remove devices.
## Installation Instructions

### Install with ansible galaxy
```
ludus ansible role add NocteDefensor.ludus_tailscale
```
### Add from this git repo
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
## Recognition and Contributions
- [@jessefmoore](https://twitter.com/jessefmoore) for the tremendous amount of patience and effort during multiple nights of testing.
