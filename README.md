# Portus on Docker compose

This docker-compose.yml is based from: 
[Portus/examples/compose - SUSE/Portus](https://github.com/SUSE/Portus/tree/2843437742515c1f0896fafaee166cde336f5b18/examples/compose)

## The hostname

This example needs the hostname in multiple places. All this has been delegated
into Compose's support of the `.env` file. For this reason, you will need to
change hostname set in this file, and also in the `nginx/nginx.conf` file.

## Certificates

This example is set up in a way so you can use self-signed certificates. Of
course this is not something you would want to do in production, but this way we
ease up the task for those who are curious to try it out.
In order to create self-signed certificates, you could use the following command:

```bash
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout portus.key -out portus.crt
```

After that, you can simply move the ``portus.key`` and the ``portus.crt`` files
into the secrets directory( `./certificates/` ).
