# tracearr

Tracearr swarm stack for ore-dock-110-4.

Deployed by the Portainer gitops workflow on ore-dock-110-4
(endpoint 3). Auto-update interval: 15m.

## Secrets

`JWT_SECRET`, `COOKIE_SECRET` and `DB_PASSWORD` are NOT in this
repo. The compose references them as `${VAR}` and Portainer
substitutes the values held in the stack environment for the
`tracearr` stack. `.env.example` documents the names.

## Volumes

The volumes are pinned with explicit `name:` entries so Swarm does
not prefix them with the stack name. The data volumes are
node-local and only exist on ore-dock-110-4, which is why all
three services are constrained to that node.
