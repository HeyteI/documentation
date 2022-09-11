# SSL setup on API server

To run the api on a local domain with ssl change `.env` file, then set it to:
```
SSL_CRT_FILE=".cert/api.heytel.local.pem"
SSL_KEY_FILE=".cert/api.heytel.local-key.pem"
WEBSERVER_SSL=true
```
Install [mkcert](https://github.com/FiloSottile/mkcert) and run the following commands:


Then run the following commands to apply ssl:
```bash
mkcert -install
mkcert -cert-file ./certs/api.heytel.local.pem -key-file ./certs/api.heytel.local-key.pem localhost api.heytel.local
```

Then you need to add the following lines to your hosts file:
```
127.0.0.1 api.heytel.local
```

`hosts` file location depends on your OS:
- Windows: `C:\Windows\System32\drivers\etc\hosts`
- Linux: `/etc/hosts`
- Mac: `/private/etc/hosts`

# SSL setup in panel

To run the api on a local domain with ssl change `.env` file, then set it to:
```
SSL_CRT_FILE=".cert/heytel.local.pem"
SSL_KEY_FILE=".cert/heytel.local-key.pem"
WEBSERVER_SSL=true
```
Install [mkcert](https://github.com/FiloSottile/mkcert) and run the following commands:


Then run the following commands to apply ssl:
```bash
mkcert -install
mkcert -cert-file ./certs/heytel.local.pem -key-file ./certs/heytel.local-key.pem localhost heytel.local
```

Then you need to add the following lines to your hosts file:
```
127.0.0.1 heytel.local
```

`hosts` file location depends on your OS:
- Windows: `C:\Windows\System32\drivers\etc\hosts`
- Linux: `/etc/hosts`
- Mac: `/private/etc/hosts`