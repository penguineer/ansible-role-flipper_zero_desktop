# Ansible Role: flipper_zero_desktop

> Set up [Flipper Zero](https://flipperzero.one/) desktop environment.

This rule installs the necessary udev rules and downloads qFlipper for
a Desktop environment.

## Usage


### Configuration

The defaults are usually suitable for installation. Feel free to change them if they do not fit your needs.


Controlling the files on the target system:

* `flipper_zero_qFlipper_target`: Path where the AppImage will be stored
* `flipper_zero_qFlipper_symlink`: Path to a symlink for version-independent access
* `flipper_zero_udev_name`: How to name the udev rule. (Modify if you want to change the priority.)


For automatic download:

* `flipper_zero_qFlipper_release`: release type, currently available are `release`, `release-candidate` and `development` (defaults to `release`)
* `flipper_zero_qFlipper_platform`: target platform, currently available are `windows/amd64`, `macos/amd64` and `linux//amd64` (defaults to `linux/amd64`)
* `flipper_zero_qFlipper_meta_url`: URL to the release meta-data


To fix the release, set:

* `flipper_zero_qFlipper_download`: URL to the qFlipper AppImage
* `flipper_zero_qFlipper_sha256`: SHA256 checksum of the AppImage file (optional, checks omitted if not defined)


Please note that this role is not suited for windows. Although the architecture `windows/amd64` and be provided, there are two different packages in the stream and the first one would be selected.


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
  - flipper_zero_…: …

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
      flipper_zero_…: …
```


## Maintainers

* Stefan Haun ([@penguineer](https://github.com/penguineer))


## Contributing

PRs are welcome!

If possible, please stick to the following guidelines:

* Keep PRs reasonably small and their scope limited to a feature or module within the code.
* If a large change is planned, it is best to open a feature request issue first, then link subsequent PRs to this issue, so that the PRs move the code towards the intended feature.


## License

[MIT](LICENSE.txt) © 2022-2025 Stefan Haun and contributors
