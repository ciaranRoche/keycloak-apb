## Requirements
- [apb](https://github.com/fusor/ansible-playbook-bundle/blob/master/README.md#installing-the-apb-tool)
- Running [catasb](https://github.com/fusor/catasb)

**NOTE:**
Due to our usage of an older version of the ASB, it is recommended using the `apb` CLI like the following:

```bash
alias apb='docker run --rm --privileged -v $PWD:/mnt -v $HOME/.kube:/.kube -v /var/run/docker.sock:/var/run/docker.sock -u $UID docker.io/feedhenry/apb'
```

Instead of the `abp` alias, you might want to use a modified alias, such as `apb-fh`, to not conflict w/ other versions that might be installed already on your machine.

## Usage
make changes to apb files in this repo and run: `make DOCKERORG="<dockerhub_org_name>" DOCKERHOST="<defaulting to docker.io>"` where dockerhub_org_name is the org referenced by your catasb (you will need to change the image name in the `apb.yml` file to match this, also).

If changes were made to the `apb.yml` file, then you will need to execute `apb bootstrap` (if this fails, then you can also run the `~/repos/catasb/local/<os>/reset_environment.sh`), though this takes a little while. Changes to the APB ansible files do not require the above step.

In the Openshift control panel, find and select the `Keycloak (APB)` and fill in the required fields. 
