# Tuwunel App Store for Runtipi

This repository contains a minimal Runtipi app store that provides a single app: Tuwunel (Matrix proxy). It follows the Runtipi `example-appstore` structure so it can be added to your Runtipi instance.

Contents:
- apps/tuwunel - App definition for Tuwunel including `config.json`, `docker-compose.json`, and metadata.


How to use
1. Create a new GitHub repository from this folder (use "Use this template" on GitHub) or push the files to a new repo.
2. In your Runtipi instance (v4.0.0+), go to Settings → App Stores → Add App Store and paste the URL of your repository (for example `https://github.com/<you>/tuwunel-appstore`).
3. Click Update App Stores in Runtipi to fetch apps from your repo.
4. Find "Tuwunel" in the apps list and click Install. Provide configuration values when prompted (e.g., `TUWUNEL_SERVER_NAME`).

Sanity checks & verification
- Ensure the `id` in `apps/tuwunel/config.json` matches the folder name `tuwunel`.
- In `apps/tuwunel/docker-compose.json` the service exposes host port 8448 -> container port 6167; adjust if that conflicts with existing services.
- After install, verify the container is running and reachable: open your browser to `https://<TUWUNEL_SERVER_NAME>:8448` or check the container logs from Runtipi.

Advanced notes
- Review and customize the env vars and volume names before installing in production.
- You can replace the image tag `ghcr.io/matrix-construct/tuwunel:latest` with a pinned tag to avoid accidental upgrades.

Verification checklist
- [ ] Push this repository to GitHub and ensure it is public or accessible to your Runtipi instance.
- [ ] Add the repository URL in Runtipi Settings → App Stores and click Update App Stores.
- [ ] Install the Tuwunel app and provide `TUWUNEL_SERVER_NAME` during install.
- [ ] Confirm the service container starts and port 8448 is reachable.

If anything fails: check `config.json` and `docker-compose.json` for JSON validity and ensure folder names match the `id`.

