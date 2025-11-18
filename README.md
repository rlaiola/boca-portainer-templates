# BOCA App Templates for Portainer

This repository provides custom **App Templates** for deploying the **BOCA – Online Contest Administrator** through Portainer.  
It extends the official Portainer templates with ready-to-use definitions specifically tailored for BOCA, enabling quick and consistent deployments.

For details on Portainer’s template system, refer to the official [documentation](https://docs.portainer.io/user/docker/templates).
For more information about BOCA, visit its upstream [repository](https://github.com/cassiopc/boca).

---

## Table of Contents

- [Overview](#overview)
- [How to Use These Templates](#how-to-use-these-templates)
- [Contributing](#contributing)
- [Code of Conduct](#code-of-conduct)
- [Security](#security)
- [License](#license)

---

## Overview

Portainer supports loading application templates from external JSON files.
By pointing Portainer to the template file from this repository, you gain access to deployment options for BOCA directly within the UI.

This repository provides:

- A **templates-2.0.json** compatible with modern Portainer versions.
- A simple and reproducible way to launch BOCA via stacks.

---

## How to Use These Templates

### Using the Portainer UI

1. Open **Settings** in Portainer.
2. Locate the **App Templates** section.
3. Set the template URL to:

```url
https://raw.githubusercontent.com/rlaiola/boca-portainer-templates/master/templates-2.0.json
```

![Alt text](/images/boca/portainer-ui.png?raw=true 'Setting app templates via Portainer UI')

4. Save the settings.

You should now see BOCA templates available in the "App Templates" panel.

### Using the [`--templates`](https://docs.portainer.io/advanced/cli#defining-your-own-app-templates) Flag

You can also start Portainer with these templates already configured:

```sh
docker run -p 9000:9000 \
           -v /var/run/docker.sock:/var/run/docker.sock \
           -v portainer_data:/data \
           -d portainer/portainer-ce:alpine \
           --templates https://raw.githubusercontent.com/rlaiola/boca-portainer-templates/master/templates-2.0.json
```

### Refreshing Templates

Portainer loads templates **only on first startup**.

If you already have a running instance and decide to use these templates later, you must clear the existing ones through either:

- the Portainer UI, or
- the Portainer [HTTP API](https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.1).

After clearing, templates will update to include BOCA options.

### Result

Once configured, Portainer will display BOCA as a deployable app template.

Example:

![App templates screenshot](/images/boca/app-templates.png?raw=true)

Using the "New Stack from Template" option, you can deploy BOCA with minimal configuration:

![New BOCA stack screenshot](/images/boca/new-stack.png?raw=true)

For full details, see the Portainer [documentation](https://docs.portainer.io/user/docker/templates/deploy-stack) on deploying stacks from templates.

---

## Contributing

If you would like to contribute to this project, please see **[CONTRIBUTING.md](CONTRIBUTING.md)**.

Before submitting a PR, you may test your code using Super-Linter:

```bash
docker run --rm \
           -e ACTIONS_RUNNER_DEBUG=true \
           -e RUN_LOCAL=true \
           -e DEFAULT_BRANCH=main \
           --env-file ".github/super-linter.env" \
           -v "$PWD":/tmp/lint \
           ghcr.io/super-linter/super-linter:latest
```

---

## Code of Conduct

See **[CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)** for community standards.

---

## Security

See **[SECURITY.md](SECURITY.md)** for vulnerability reporting instructions.

---

## License

Copyright Universidade Federal do Espirito Santo (Ufes)

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <https://www.gnu.org/licenses/>.

This program is released under license GNU GPL v3+ license.
