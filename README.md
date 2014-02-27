# No Trolls Allowed wiki

Event wiki. More information regarding event on our website [notrollsallowed.com](http://notrollsallowed.com "No Trolls Allowd")].

## How to install

Copy `config.example.php` to `config.php` and edit values inside file.

Nginx rewrite rules:

```nginx
server {
    ...
    location / {
        index index.php;
        error_page 404 = @wiki;
    }

    location @wiki {
        rewrite ^/(.*)$ /index.php?title=$1&$args;
    }
    ...
}
```
