Steps:

- Copy the `services.yaml.example` to `services.yaml`. Edit the username for permission to access CI to be your GitHub username.
- Create an [oauth2 application](https://github.com/settings/developers). Put the client id & secret into the `services.yaml` at the appropriate spot. Be sure to set your redirect URL as `https://localhost/uisvc/login` in the oauth2 application.
- `docker-compose up -d`. You may actually have to do this twice due to a bug in compose or docker, no idea. Repeat until all the containers have booted, although `migrator` only needs to boot once and quit.
- Visit https://localhost -- you should be presented with a login page.

If you see this you've succeeded:

![splash screen](splash.png)

From here, you can add your repository and configure it. Check out the [Repository Config](https://tinyci.org/docs/repository_config) documentation for more information.

When you're done: `docker-compose down`. This will tear down all containers, but some files will be left over. They are dot-files in the directory, you can spot them easily with `ls -a`. Remember, some of them will be owned by `root` so you will need `sudo` to remove them.
