# Unraid Templates

Personal collection of Unraid Community Applications (CA) templates, and the supporting Docker images they use.

## Templates

### couchdb-livesync

CouchDB 3.3.3 pre-configured for [Obsidian Self-Hosted LiveSync](https://github.com/vrtmrz/obsidian-livesync). On first boot, all required CouchDB settings for LiveSync are applied automatically, so there are no manual steps in the CouchDB admin UI.

- Template file: [`couchdb-livesync.xml`](./couchdb-livesync.xml)
- Docker image: [`heyitsbrian/couchdb-livesync`](https://hub.docker.com/r/heyitsbrian/couchdb-livesync)
- Upstream LiveSync plugin: https://github.com/vrtmrz/obsidian-livesync

## Installing a template on Unraid

1. Open the Unraid web UI and go to **Docker** > **Add Container**.
2. In the **Template** field, paste the raw URL of the template, for example:
   ```
   https://raw.githubusercontent.com/hey-its-brian/unraid-templates/main/couchdb-livesync.xml
   ```
3. Fill in the required variables (admin username, password, database name, paths, port).
4. Click **Apply**. Unraid will pull the image and start the container.

Once running, the CouchDB admin UI is at `http://<unraid-ip>:5984/_utils`.

## Building the Docker image

The `build-and-push.sh` script builds the `heyitsbrian/couchdb-livesync` image and pushes it to Docker Hub.

```bash
./build-and-push.sh           # builds and tags as 3.3.3 and latest
./build-and-push.sh 3.3.3     # explicit version
```

Requires Docker and a Docker Hub account with push access to the target repository.

## License

MIT
