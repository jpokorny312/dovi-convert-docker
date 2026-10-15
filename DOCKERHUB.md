# Veröffentlichung auf Docker Hub

Das Image wird automatisch von `.github/workflows/` gebaut und gepusht (amd64 + arm64).

## Einmalige Einrichtung
1. Konto auf https://hub.docker.com anlegen und ein Repository erstellen, z. B. `<user>/dovi-convert`.
2. Docker Hub → Account Settings → Security → **New Access Token** (Rechte: Read & Write).
3. GitHub-Repo → Settings → Secrets and variables → Actions:
   - `DOCKERHUB_USERNAME` = Docker-Hub-Benutzername
   - `DOCKERHUB_TOKEN` = der Access Token
4. In `.github/workflows/*.yml` `IMAGE_NAME` auf `<user>/dovi-convert` ändern
   (aktuell: `smidley/dovi-convert`) und in `docker-compose.yml` / `unraid/` anpassen.

## Release
```bash
git checkout main && git pull
git tag v1.2.0 && git push origin v1.2.0
```
Der Tag löst den Workflow aus und veröffentlicht die Tags `1.2.0`, `1.2` und `latest`.
Danach auf GitHub unter Releases → *Draft a new release* den Tag auswählen.

## Manuell (ohne GitHub Actions)
```bash
docker login
docker buildx create --use
docker buildx build --platform linux/amd64,linux/arm64 \
  -t <user>/dovi-convert:1.2.0 -t <user>/dovi-convert:latest --push .
```
