# ntfy

Push notifications made easy

## Configuration

### Adding a user

```bash
ntfy user add --role=admin <username>
password: <password>
confirm: <password>
user added with role admin
```

### UnifiedPush

For configuring for UnifiedPush the following commands can be used:

```bash
ntfy access '*' 'up*' write-only
```
