# Role: flatpak

## Description

This role will ensure flatpak is installed, configure the flathub repo, and install the specified flatpaks. Some distributions. i.e. Fedora, filter the repository from [flathub.org](https://flathub.org/home) to curate the selection from Gnome Software, a unfiltered remote repository can be created for the user's convenience.

## Role variables and their default values

The `flatpak_required_packages` variable is a list of the packages to install flatpak from the ditro repositories.

**`flatpak_required_packages`** (list): Fedora default => `['flatpak', 'flatpak-libs', 'flatpak-selinux', 'flatpak-session-helper' ]`

The `flatpak_required_apps` is a list of dictionaries that contain the name of the flatpak to install, the state (`present` or `absent`), method (`user` or `system`), and the remote flatpak repository.

**`flatpak_apps`** (list of dictionaries): Default => `undefined`

The dictionaries `flatpak_apps` expect have the keys as follows:
- **`name`** (string): The fully qualified name of the app to install (e.g. `com.valvesoftware.Steam`)
- **`state`** (string): Either `present` (default) or `absent`
- **`method`** (string): Either `user` (default) or `system`
- **`remote`** (string): The name of the flatpak repository to use - Default => `unfiltered-flathub` (created by this role)

## Example playbook usage
```
- name: Setup required environment
  hosts: all
    
  roles:
  - role: theliomcfly.workstation.flatpak
      tags: flatpak
      become: true
      flatpak_apps:
        - name: com.valvesoftware.Steam
        - name: us.zoom.Zoom
        - name: net.cozic.joplin_desk
        - name: com.visualstudio.code
        - name: com.github.tchx84.Flatseal
        - name: org.gnome.Extensions
        - name: org.zealdocs.Zeal
```

# References
- https://github.com/ThelioMcFly/ansible-workstation/tree/main/roles/flatpak

