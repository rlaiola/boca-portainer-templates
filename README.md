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
           --templates https://raw.githubusercontent.com/rlaiola/portainer-templates/master/templates-2.0.json
```

Templates are loaded once when Portainer is first started. If you already deployed a Portainer instance then decide to use these templates, you’ll need to clear the default templates either in the user interface or through the [HTTP API](https://app.swaggerhub.com/apis/portainer/portainer-ce/2.19.1).

## Result

![Alt text](/images/boca/app-templates.png?raw=true "Portainer app templates list")

![Alt text](/images/boca/new-stack.png?raw=true "New BOCA stack from template")

For more information on how to deploy a stack from a template, see the [documentation](https://docs.portainer.io/user/docker/templates/deploy-stack).
