> [!IMPORTANT]
> **This repo is moving to Nostr.** GitHub will stay as a mirror. New issues and patches go there.
>
> - Browse: [gitworkshop.dev/nomadshiba.me/podman-devcontainer](https://gitworkshop.dev/nomadshiba.me/podman-devcontainer)
> - Clone: `git clone nostr://nomadshiba.me/podman-devcontainer`
>
> To clone `nostr://` URLs and send patches, install [ngit](https://ngit.dev). It's git collaboration over Nostr, with no accounts and no platform.
>
> <sub>If NIP-05 doesn't resolve: [gitworkshop (npub)](https://gitworkshop.dev/npub1gkp4cdh5rktehjqjnqc09awey4302dpadlka6mes4fu5spes7fhqfsppqk/podman-devcontainer) · `nostr://npub1gkp4cdh5rktehjqjnqc09awey4302dpadlka6mes4fu5spes7fhqfsppqk/podman-devcontainer`</sub>

# podman-devcontainer

A simple `podman` wrapper to make it work with DevContainers. Just a quick way to get Podman playing nice with your dev setup.  

## Usage  

1. Create a script file at `~/.local/bin/podman-devcontainer` (or anywhere in your `PATH`).  
2. Copy-paste the script in.  
3. In VS Code, add this to your settings (or do something similar in your editor):  
   ```json
   {
     "dev.containers.dockerPath": "podman-devcontainer"
   }
   ```  
4. Done! 🎉  

### Using with Distrobox  

If you're running `distrobox`, you'll want to create another wrapper to make sure it runs outside the container:  

```bash
#!/bin/bash
distrobox-host-exec podman-devcontainer "$@"
```  

This ensures `podman-devcontainer` runs on the host instead of inside `distrobox`.  

*Personally, I use a separate home directory for `distrobox`, which makes keeping things organized even easier.*

---

Been using this setup for over a year—zero issues. Works like a charm! 🚀  

## License

[MIT](LICENSE)
