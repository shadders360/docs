# Dev container

The file `.devcontainer/devcontainer.json` controls and builds a docker environment which can
be used as development environment within vscode. As it runs in a docker container it is platform independent and isolates 
all the problem of version mismatching. Everybody has the same setup, no more it works on mine !

you can read more about [devcontainers here](https://code.visualstudio.com/docs/devcontainers/containers)

You will need to have a .gitconfig (which gets pulled into the container) or you can set your email and name for BB commits 
in the `devcontainer.json file`

The following directories are mounted into the container:

* {localEnv:HOME}/.dvla/ any personal files you may need for example ansible vault keys
* {localEnv:HOME}/.ssh/ will contain your BB ssh key for non password commits [see](https://support.atlassian.com/bitbucket-cloud/docs/set-up-personal-ssh-keys-on-windows/#Create-an-SSH-key-pair)

## version 

To change a feature you can add Key value pairs for the required setting. 

In this example Terraform has been pinned to 1.4.2. Keep this in line with the drone version !!

```shell
    "ghcr.io/devcontainers/features/terraform:1": {
            "version" : "1.4.2",
            // "terragrunt" : "0.45.3", uncomment for version otherwise use latest 
            "installTFsec" : true,
            "installTerraformDocs" : true
    }
```

## software

This image has the following installed software

* [terraform] (https://www.terraform.io/)
* [terragrunt](https://terragrunt.gruntwork.io/)
* [tflint](https://github.com/terraform-linters/tflint)
* [tfsec](https://aquasecurity.github.io/tfsec)
* [terraform-docs](https://github.com/terraform-docs/terraform-docs)

example command `terraform-docs markdown table --output-file README.md --output-mode inject .`
