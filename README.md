# Transactional Mail

This repo contains a shell script for the `mail-transaction` command. This is a Linux command to send transactional mail via GC Notify.

## Installation

1. Pull the repo into any directory
1. Add that directory into your `PATH` variable
1. Link the autocompletion script to your bash completions: `sudo ln -s $(dirname "$(which mail-transaction)")/autocomplete /etc/bash_completion.d/mail-transaction` (you may need to restart your shell afterwards)
1. Set the GC Notfiy API key: `mail-transaction set-api-key <API-Key>`

## Examples

### In the Command Line

```
mail-transaction send <TEMPLATE_ID> <RECIPIENT> {\"name\":\"Jeffy\"\,\"country\":\"Canada\"}
```

### In a Shell Script

````
personalisation_data=$(echo {\"name\":\"Jeffy\"\,\"country\":\"Canada\"})
mail-transaction send <TEMPLATE_ID> <RECIPIENT> "$(echo "$personalisation_data")" || true
````
