# Basic Maintenance Page

This is a basic maintenance page for when you need to take down a service and you want to keep your users informed.

## Acknowledgements

* [abiosoft/caddy](https://hub.docker.com/r/abiosoft/caddy/)
* [Docker](https://www.docker.com/)
* [HTML: Simple Maintenance Page](https://gist.github.com/pitch-gist/2999707)


## Requirements

* A server running Docker that can bind to port 80 and 443
* [A valid domain that meets the following criteria.](https://caddyserver.com/docs/automatic-https)

## Instructions

### Clone this repository:

```
git clone https://github.com/dantontech/basicMaintenancePage.git
```

### Switch to the respository directory:

```
cd basicMaintenancePage
```

### Switch to the cfg directory:

```
cd cfg
```

Using your preferred editior, change the following information in Caddyfile.  Change line 1 to be your domain.  Change line 2 to be your email address after tls.

### Switch to the srv directory:

```
cd .. && cd srv
```

Using your preferred editior, change the following information in index.html.  Change line 15 to have your email address.  Change line 16 to have your team name.

### Switch back to the root of the git repository:

```
cd ..
```

### Run the following command:

```
docker run --name basicMaintenancePage -d -e ACME_AGREE=true -v $(pwd)/cfg/Caddyfile:/etc/Caddyfile -v $(pwd)/srv:/srv -p 80:80 -p 443:443 abiosoft/caddy
```

If all is well you should see your maintainence page at the domain you configured above.
