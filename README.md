<h1>Bird API Kubernetes</h1>

This repo hosts the list of configuration files that are used to deploy the entire bird backend. There are a few other things that would be required for a functional deployment. First, you need a neo4j database. We recommend AuraDB, the managed database by the Neo4j team on GCP. Secondly, you'll need a handful of config files. Please create and fill the following secret files out accordingly and **DO NOT SHARE THEM OR THEIR CONTENTS**:

`/jwt-secrets.yml`:

```
apiVersion: v1
kind: Secret
metadata:
  name: jwt-secrets
type: Opaque
data:
  access_secret: <secret>
  refresh_secret: <secret>
```

`/permission/redis/secret.yml`:

```
apiVersion: v1
kind: Secret
metadata:
  name: permission-redis-secrets
type: Opaque
data:
  username: <username>
  password: <password>
  port: "6379"
```

`/neo4j-secrets.yml`:

```
apiVersion: v1
kind: Secret
metadata:
  name: neo4j-secret
type: Opaque
data:
  neo4j_uri: neo4j+s://link-to-neo4j-db
  neo4j_port: "7687"
  neo4j_username: <neo4j>
  neo4j_password: <password>

```
