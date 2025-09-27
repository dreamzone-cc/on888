Tuwunel is a Matrix homeserver proxy that helps with federation and deployment patterns. This Runtipi package uses the official Tuwunel OCI image and exposes the federation port (8448).

Configuration
- TUWUNEL_SERVER_NAME: Set your server's hostname (e.g. chat.example.com)
- TUWUNEL_ALLOW_REGISTRATION: true/false to allow account registration

Refer to the upstream docs at https://tuwunel.chat/deploying/docker.html for full deployment options and advanced configurations.
