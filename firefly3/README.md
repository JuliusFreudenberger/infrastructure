# fireflyiii

Firefly III is a manager for your personal finances.
It is self-hosted and open source.
This means that it's free, it has no ads and no tracking.

## Important step when deploying
Several environment variables have to be set:
- firefly_version
- postgres_version
Firefly specific:
- APP_KEY: A random string of exactly 32 chars
- STATIC_CRON_TOKEN: A random string of exactly 32 chars
- MAIL_PASSWORD: The password for the mail account

