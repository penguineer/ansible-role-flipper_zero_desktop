# Ansible Role: flipper_zero_desktop

> Set up [Flipper Zero](https://flipperzero.one/) desktop environment.

This rule installs the necessary udev rules and downloads qFlipper for
a Desktop environment.

## Usage


### Configuration

Please note that all variables have default values and usually do not need to be changed.

* `flipper_zero_qFlipper_download`: URL to the qFlipper AppImage
* `flipper_zero_qFlipper_target`: Path where the AppImage will be stored
* `flipper_zero_qFlipper_symlink`: Path to a symlink for version-independent access
* `flipper_zero_udev_name`: How to name the udev rule. (Modify if you want to change the priority.)

### Requirements

Add to your `requirements.yml`:
```yml
- src: penguineer.flipper_zero_desktop
  version: version-tag
```

### Include

as role:

```yaml
vars:
  - flipper_zero__…: …

roles:
  - role: penguineer.flipper_zero_desktop
```

as task:

```yaml
tasks:
  - name: Set up Flipper Zero environment
    include_role:
      name: penguineer.flipper_zero_desktop
    vars:
      flipper_zero__…: …
```


## Maintainers

* Stefan Haun ([@penguineer](https://github.com/penguineer))


## Contributing

PRs are welcome!

If possible, please stick to the following guidelines:

* Keep PRs reasonably small and their scope limited to a feature or module within the code.
* If a large change is planned, it is best to open a feature request issue first, then link subsequent PRs to this issue, so that the PRs move the code towards the intended feature.


## License

[MIT](LICENSE.txt) © 2022 Stefan Haun and contributors
