---
slug: /cloud-providers/civo
title: Civo
sidebar_label: Civo
---

# Civo

## Supported resources
- Compute instances
- Kubernetes clusters
- Firewalls
- LoadBalancers
- Networks
- Object stores
- Volumes

## Local Komiser CLI (Single account)

Komiser now supports multiple cloud accounts by default. Account configuration is done through the `config.toml` file, just pass in your account `API Token`.

We've also added 2 methods of persisting your account data.
### Postgres
#### Add to config.toml file
```
[postgres]
uri="postgres://postgres:komiser@localhost:5432/komiser?sslmode=disable"
```
### SQLite

```
[sqlite]
  file = "komiser.db"
```

### Configuring Credentials

Firstly grab your API key from your Civo account.
Under `Profile/Security/API key`
Need help finding it? Head on over to the official Civo [documentation](https://www.civo.com/docs/account/api-keys).

### Add your Civo API token to your confuriation file

```
[[civo]]
name="demo-account"
token="yourApiTokenHere"

[sqlite]
file="komiser.db
```
                                        

### Run it!
* That should be it. Try out the following from your command prompt to start the server:

```
komiser start 
```

* Point your browser to `http://localhost:3000`

## Local Komiser CLI (Multiple accounts)
Simply add more authentication blocks to the configuration file

```
[[civo]]
name="demo-account"
token="yourApiTokenHere"

[[civo]]
name="sandbox"
token="yourSandboxApiTokenHere"

[[civo]]
name="production"
token="yourProductionApiTokenHere"

[sqlite]
file="komiser.db
```

### Watch Civo integration tutorial
<div style={{
    position: 'relative',
    paddingBottom: '56.25%',
    paddingTop:'30px',
    height:0,
    overflow:'hidden',
  }}>
  <iframe
    src='https://www.youtube.com/embed/NBbEpoW-kVs'
    allowFullScreen
    webkitallowfullscreen="true"
    frameBorder="0"
    style={{
      position: 'absolute',
      top:0,
      left:0,
      width:'100%',
      height:'100%',
    }}
  >
  </iframe>
</div>