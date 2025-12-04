# infrahub-anta-transform

This repo contains python transform, query and artifact defintions.
They can be used by Infrahub to create artifacts which will run a Kriten job.

## Testing

Set env vars to connect to infrahub:
```
export INFRAHUB_ADDRESS="http://192.168.10.59:8000"
export INFRAHUB_API_TOKEN="187e1116-9c18-0d09-3862-c51320cdb9b7"
source venv/bin/activate
```

Run infrahubctl:
```
infrahubctl transform switch_check_transform name=lon-lab-arlf01 --branch main
```


## Instructions

Make sure the object that contains the artifact inherits from CoreArtifactTarget (See schema.yml)

Add a standard group in Infrahub -> Object Management > Groups
Group name must match "targets" in artifact definition in .infrahub.yml
Add switches as members of the group

Add this repository in Infrahub -> Integrations > Git Repositories

Kriten job runs anta_runner.py from repo https://github.com/Kubecode-io/infrahub-anta-demo
