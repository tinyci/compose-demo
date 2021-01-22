Steps:

- Copy the `services.yaml.example` to `services.yaml`.
- Create an [oauth2 application](https://github.com/settings/developers). Put the client id & secret into the `services.yaml` at the appropriate spot. Be sure to set your redirect URL as `https://localhost/uisvc/login` in the oauth2 application.
- `docker-compose up -d`. You may actually have to do this twice due to a bug in compose or docker, no idea. Repeat until all the containers have booted, although `migrator` only needs to boot once and quit.
- Visit https://localhost -- you should be presented with a login page.
- From here, you can add your repository and configure it. Check out the [Repository Config](https://tinyci.org/docs/repository_config) documentation for more information.
