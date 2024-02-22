# App Templates For BOCA

This repository extends the official templates (**'Apps Templates'**) definitions for Portainer with the BOCA Online Contest Administrator (simply known as BOCA), an administrative system designed for orchestrating programming contests.

For more information about the template definition format and how to create templates, see the [relevant documentation section](https://docs.portainer.io/user/docker/templates). For in-depth information regarding BOCA, please visit its official [repository](https://github.com/cassiopc/boca).

## Ways To Use BOCA Templates

**... via Portainer UI**

In the _Settings_ menu, update the URL of _App Templates_ with `https://raw.githubusercontent.com/rlaiola/boca-portainer-templates/master/templates-2.0.json` and _Save application settings_.
![Alt text](/images/boca/portainer-ui.png?raw=true "Setting app templates via Portainer UI")

**... or with the [--templates](https://docs.portainer.io/advanced/cli#defining-your-own-app-templates) flag**

```sh
docker run -p 9000:9000 \
           -v /var/run/docker.sock:/var/run/docker.sock \
           -v portainer_data:/data \
           -d portainer/portainer-ce:alpine \
           --templates https://raw.githubusercontent.com/rlaiola/boca-portainer-templates/master/templates-2.0.json
```

Templates are loaded once when Portainer is first started. If you already deployed a Portainer instance then decide to use these templates, you’ll need to clear the default templates either in the user interface or through the [HTTP API](https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.1).

### Result

![Alt text](/images/boca/app-templates.png?raw=true "Portainer app templates list")

![Alt text](/images/boca/new-stack.png?raw=true "New BOCA stack from template")

For more information on how to deploy a stack from a template, see the [documentation](https://docs.portainer.io/user/docker/templates/deploy-stack).

## How To Contribute

If you would like to help contribute to this project, please see [CONTRIBUTING](https://github.com/rlaiola/boca-portainer-templates/blob/master/CONTRIBUTING.md).

Before submitting a PR consider building and testing a Docker image locally and checking your code with Super-Linter:

  ```sh
  docker run --rm \
             -e ACTIONS_RUNNER_DEBUG=true \
             -e RUN_LOCAL=true \
             --env-file ".github/super-linter.env" \
             -v "$PWD":/tmp/lint \
             ghcr.io/super-linter/super-linter:latest
  ```

## License

Copyright Universidade Federal do Espirito Santo (Ufes)

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.

This program is released under license GNU GPL v3+ license.

## Support

Please report any issues with _boca-portainer-templates_ at [https://github.com/rlaiola/boca-portainer-templates/issues](https://github.com/rlaiola/boca-portainer-templates/issues)
