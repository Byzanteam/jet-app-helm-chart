# Jet App

## Installation

### make `values.local.yaml`
1. set imageCredentials for image pulling
```yaml
# values.local.yaml
imageCredentials:
  registry: registry.cn-hangzhou.aliyuncs.com
  username: deploy-man@skylark
  password: changeit
```

2. set image info for image pulling
```yaml
# values.local.yaml

image:
  repository: jet/jet-app
  tag: "latest"
  pullPolicy: IfNotPresent
```

3. set host and environments for app
```yaml
# values.local.yaml

# Application
appHost: app.jet.localhost

# Frontend environments
baseUrl: /
jetEndpoint: https://beta.jet.work

```

4. set actionList
```yaml
# values.local.yaml

actionList: |-
  # action
  ACTION_NAME=val
```

### make install
```bash
# set release-name in `.env` file

# .env
RELEASE=app-release-name

make install
```

```bash
# set release-name
make install RELEASE=app-release-name
```

## HowTo

### Setup TLS
```yaml
# values.local.yaml

appTLSSecret:
  certificate: base64 encoded certificate-file
  key: base64 encoded key-file
```

### Setup Sentry
```yaml
# values.local.yaml

sentryDsn: "sentry-dsn"
sentryRelease: "unique-release-name"
```
