# teleport 

The easiest, most secure way to access infrastructure.

## Deploying
### Adding the teleport apt repo
```bash
$ sudo curl https://deb.releases.teleport.dev/teleport-pubkey.asc -o /usr/share/keyrings/teleport-archive-keyring.asc
$ echo "deb [signed-by=/usr/share/keyrings/teleport-archive-keyring.asc] https://deb.releases.teleport.dev/ stable main" | sudo tee /etc/apt/sources.list.d/teleport.list
```

### Updating and installing teleport
```bash
$ sudo apt update
$ sudo apt install teleport
```

### Installing as server
Copy the `teleport.yaml` to `/etc/teleport.yaml`.

Start the teleport service.

### Adding a node
Copy the `teleport-node.yaml` to `/etc/teleport.yaml`.
On the teleport server create a new invitation token:
```bash
$ sudo tctl tokens add --type=node
```
Copy the auth_token and ca_pin and insert in the `teleport.yaml`.
Change the node name.

Start the teleport service.
