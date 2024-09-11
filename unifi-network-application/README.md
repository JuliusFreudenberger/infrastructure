# unifi-network-application

Powerful, enterprise wireless software engine ideal for high-density client deployments requiring low latency and high uptime performance

## Important step when deploying
The user to be used by unifi has to be created by an init script.
Use the following script mounted in the container like so:
`/path/to/init-mongo.sh:/docker-entrypoint-initdb.d/init-mongo.sh:ro`

```bash
#!/bin/bash

if which mongosh > /dev/null 2>&1; then
  mongo_init_bin='mongosh'
else
  mongo_init_bin='mongo'
fi
"${mongo_init_bin}" <<EOF
use ${MONGO_AUTHSOURCE}
db.auth("${MONGO_INITDB_ROOT_USERNAME}", "${MONGO_INITDB_ROOT_PASSWORD}")
db.createUser({
  user: "${MONGO_USER}",
  pwd: "${MONGO_PASS}",
  roles: [
    { db: "${MONGO_DBNAME}", role: "dbOwner" },
    { db: "${MONGO_DBNAME}_stat", role: "dbOwner" }
  ]
})
EOF
```
