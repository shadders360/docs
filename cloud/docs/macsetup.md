# New MAC setup

Things I did with my new MAC m2

## Installed software

Install [BREW](https://brew.sh/)

1. installed Visual studio code ARM version
2. synced my visual code settings via the synced setting option
3. install GIT as part of MACOS code tools
4. https://aws.amazon.com/cli/  via mac install (not via brew)
5. shortcut tool `brew install --cask maccy` [see](https://www.macupdate.com/app/mac/60683/maccy)
6. iterm2 `brew install --cask iterm2`
7. install [oh-my-zsh](https://blog.larsbehrenberg.com/the-definitive-iterm2-and-oh-my-zsh-setup-on-macos)
8. brew install tree
9. brew install [rectangle](https://rectangleapp.com/)
10. brew install fig [fig](https://fig.io/)
11. brew install buildpacks/tap/pack

## Docker install

1. install docker desktop - [mac install](https://docs.docker.com/desktop/install/mac-install/)
2. install Rosetta 2
3. enabled rosetta intel compatibility  mode in docker desktop settings

## docker known issues

read here https://docs.docker.com/desktop/troubleshoot/known-issues/

https://github.com/puppeteer/puppeteer/blob/main/docs/troubleshooting.md#chrome-headless-doesnt-launch

https://github.com/aws-azure-login/aws-azure-login/blob/main/Dockerfile

>
> Some images do not support the *ARM64* architecture. You can add --platform linux/amd64 to run (or build) an Intel image using emulation.
> However, attempts to run Intel-based containers on Apple silicon machines under emulation can crash as qemu sometimes fails to run the container. In addition, filesystem change notification APIs (inotify) do not work under qemu emulation. Even when the containers do run correctly under emulation, they will be slower and use more memory than the native equivalent.
> In summary, running Intel-based containers on Arm-based machines should be regarded as “best effort” only. We recommend running arm64 containers on Apple silicon machines whenever possible, and encouraging container authors to produce arm64, or multi-arch, versions of their containers. We expect this issue to become less common over time, as more and more images are rebuilt supporting multiple architectures.

started simple container

built a dev container for azure with terraform Fell over :)

```bash
Run: docker buildx build --load --build-arg BUILDKIT_INLINE_CACHE=1 -f /tmp/devcontainercli-root/container-features/0.31.0-1680114150412/Dockerfile-with-features -t vsc-azure-terraform-72555ab33a6a677065297d206244c9f1 --target dev_containers_target_stage --build-arg TERRAFORM_VERSION=0.14.5 --build-arg TFLINT_VERSION=0.24.1 --build-arg TERRAGRUNT_VERSION=0.28.1 --build-arg _DEV_CONTAINERS_BASE_IMAGE=dev_container_auto_added_stage_label /workspaces/azure-terraform/.devcontainer
```

```bash
docker run --platform linux/amd64 --rm -it -v ~/.aws:/root/.aws dtjohnson/aws-azure-login --profile azure

```

## Other software may look at

[Notion](https://www.notion.so/product)
[Bitwarden](https://bitwarden.com/)
[buildpacks](https://buildpacks.io/)