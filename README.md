# FreeBSD Vagrant Action

**The value for [runs-on](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idruns-on) must either be set to `macos-13` or `ubuntu-latest` in order to use this action.**

This action allows the running of command-line programs via the `bash` shell of FreeBSD VMs provisioned with Vagrant using the [run](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idstepsrun) keyword. This also works with composite actions which exclusively use the `run` keyword (and/or call other composite actions which also do so.)

#### *This action is currently only tested with these boxes (but will probably also work with others):*
  * `freebsd/FreeBSD-12.4-STABLE` (`macos-13` only)
  * `freebsd/FreeBSD-13.3-STABLE` (`macos-13` only)
  * `freebsd/FreeBSD-14.1-STABLE` (`macos-13` only)
  * `generic/freebsd12`
  * `generic/freebsd13`
  * `generic/freebsd14`

# Usage
<!-- start usage -->
1. Provision a `FreeBSD VM` using the specified `box` (with 2 CPUs & 2GB of RAM)
    ```yaml
    - name: Provision VM
      uses: hummeltech/freebsd-vagrant-action@v1.4
      with:
        box: freebsd/FreeBSD-12.4-STABLE
        cpus: 2
        memory: 2048
    ```
2. Execute a command using the `run` keyword
    ```yaml
    - name: Display the contents of /etc/os-release
      run: cat /etc/os-release
    ```
<!-- end usage -->
