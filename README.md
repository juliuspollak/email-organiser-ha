# Personal Email Organiser — Home Assistant repository

This is the public **installation metadata** repository. Application source and development are maintained privately in `juliuspollak/email-organiser`.

## Install source

Add this repository URL in Home Assistant **Settings → Apps → App store → ⋮ → Repositories**:

`https://github.com/juliuspollak/email-organiser-ha`

The app manifest is at `email_organiser/config.yaml` and refers to the published ARM64 image `ghcr.io/juliuspollak/email-organiser:1.1.2`.

## Migration warning

**Do not start the new app until migration is complete.** Your existing local app and this repository app have different Supervisor identifiers, so the new app does not automatically inherit files under `/addon_configs/local_email_organiser`. Preserve your existing `accounts.json`, Gmail token, Yahoo password and user rules. Never commit these files to GitHub.

For the first test, disable automatic actions, unsubscribe and deletion. Only start the replacement app after credentials have been migrated to its own app-config directory, and the previous app has been stopped. An image build passing does **not** establish successful mailbox integration.

## Maintenance

Release `config.yaml` `version` must match the published image tag. Publish and verify the image before changing the manifest version. This repository must never contain personal mailbox data, tokens or app passwords.
