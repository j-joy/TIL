### Running application(node, heroku, ...) setting on GO agent

Override default environment by :

Overriding them using a file ~/Library/Application Support/Go Agent/overrides.env. This file is sourced during agent startup, and it can be setup to change environment variables.

```bash
PATH=$PATH:/usr/local/bin
```
https://docs.gocd.org/current/installation/install/agent/osx.html
