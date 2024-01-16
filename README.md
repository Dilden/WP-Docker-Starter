# WP Docker Starter Template

This `docker compose` template intends to be helpful when developing or working with WordPress locally. It comes with WordPress, MariaDB, PHPMyAdmin, and WP-CLI.

## How to Use
WordPress site will be available at http://localhost:8000.
PHPMyAdmin will be available at http://localhost:8080.

### Useful commands
To make DB changes, execute them in the WP-CLI container like so:
`docker exec NAME_HERE-wpcli wp search-replace "ORIGINAL_SITE_URL_HERE" "http://localhost:8000" --precise --recurse-objects --all-tables --dry-run` to see how many replacements need to be made. To run it, remove the --dry-run option. `NAME_HERE` should be replaced with the name given in the .env.

## Known Issues
There is a known permissions issue. When making changes to the filesystem via the WP Admin interface, the folder in which WordPress is installed will need to have www-data set as the owner and group. This can be achieved with `chown -R www-data:www-data .`. Likewise, when editing locally, your local user will need to have ownership.
