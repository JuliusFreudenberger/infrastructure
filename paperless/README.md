# paperless-ngx

Paperless-ngx is a community-supported open-source document management system that transforms your physical documents into a searchable online archive so you can keep, well, less paper.

## Important step when deploying
Several environment variables have to be set:
- paperless_version
- postgres_version
Paperless specific:
- PAPERLESS_SECRET_KEY: A random string
- PAPERLESS_URL: The URL of the paperless instance (used for CSRF, CORS)
- PAPERLESS_LOGOUT_REDIRECT_URL: The URL for logging out of SSO
