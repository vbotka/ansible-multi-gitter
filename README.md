# multi_gitter

[![quality](https://img.shields.io/ansible/quality/27910)](https://galaxy.ansible.com/vbotka/multi_gitter)
[![Build Status](https://app.travis-ci.com/vbotka/ansible-multi-gitter.svg?branch=master)](https://app.travis-ci.com/vbotka/ansible-multi-gitter)
[![GitHub tag](https://img.shields.io/github/v/tag/vbotka/ansible-multi-gitter)](https://github.com/vbotka/ansible-multi-gitter/tags)

[Ansible role vbotka.multi_gitter](https://galaxy.ansible.com/vbotka/multi_gitter/). Install and configure [multi-gitter](https://github.com/lindell/multi-gitter/).


## Supported platforms

This role has been tested with:

* [Ubuntu Supported Releases](http://releases.ubuntu.com/)

Other Linux distros should work out of the box with minimal update of the role's variables.

Feel free to [share your feedback and report issues](https://github.com/vbotka/ansible-multi-gitter/issues).

[Contributions are welcome](https://github.com/firstcontributions/first-contributions).


## Install the role

```bash
shell> ansible-galaxy role install vbotka.multi_gitter
```


## Role Variables

See the defaults. Fit the variables to your needs.


## Workflow

Create a playbook

```bash
shell> cat multi-gitter.yml
- hosts: remote_host
  become: true
  roles:
    - vbotka.multi-gitter
```

Test the syntax

```bash
shell> ansible-playbook multi-gitter.yml --syntax-check
```

Display the variables

```bash
shell> ansible-playbook multi-gitter.yml -t mg_debug -e mg_debug=true
```

Install multi-gitter

```bash
shell> ansible-playbook multi-gitter.yml
```


## Trouble shooting

The role provides tags to step through the tasks and localize the
problem if necessary

* Create directory for the source *mg_tmpdir*

```bash
shell> ansible-playbook multi-gitter.yml -e mg_debug=true -t mg_source_dir
```

* Download the source *mg_tarball* and the checksums *mg_checksums*

```bash
shell> ansible-playbook multi-gitter.yml -e mg_debug=true -t mg_source_download
```

* Untar the tarball

```bash
shell> ansible-playbook multi-gitter.yml -e mg_debug=true -t mg_source_untar
```

* Install the binary

```bash
shell> ansible-playbook multi-gitter.yml -e mg_debug=true -t mg_install_binary
```

* Install the completions

```bash
shell> ansible-playbook multi-gitter.yml -e mg_debug=true -t mg_install_completions
```


### Ansible lint

Use the configuration file *.ansible-lint.local* when running
*ansible-lint*. Some rules might be disabled and some warnings might
be ignored. See the notes in the configuration file.

```bash
shell> ansible-lint -c .ansible-lint.local
```


## References

- [multi-gitter](https://github.com/lindell/multi-gitter/)


## License

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


## Author Information

[Vladimir Botka](https://botka.info)
