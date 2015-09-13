# Ansible Role: nodejs

[![BuildStatus](https://travis-ci.org/JhovaniC/ansible-role-nodejs.svg?branch=master)](https://travis-ci.org/JhovaniC/ansible-role-nodejs)

Installs nodejs on Debian/Ubuntu.

## Requirements

None

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    nodejs_version: "0.12"

The Node.js version to install. "0.12" is the default.

    nodejs_forever: true

Whether to install Forever, a simple process manager for nodejs. With forever installed, you can start a nodejs app with the command `forever start /path/to/app.js`, and manage the app via `forever` much the same as you would manage services on your server with `service`.

    nodejs_npm_global_packages: []

Add a list of npm packages with a `name` and (optional) `version` to be installed globally. For example:

    nodejs_npm_global_packages:
      # Install a specific version of a package.
      - name: gulp
        version: 3.9.0
      # Install the latest stable release of a package.
      - name: node-sass

## Dependencies

None.

## Example Playbook

    - hosts: servers
      vars_files:
        - vars/main.yml
      roles:
        - JhovaniC.nodejs

*Inside `vars/main.yml`*:

    nodejs_forever: true
    nodejs_npm_global_packages:
      - name: gulp
      - name: node-sass

## License

BSD / MIT
