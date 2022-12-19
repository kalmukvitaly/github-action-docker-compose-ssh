```
name: Deploy

on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@main

    - uses: kalmukvitaly/github-action-docker-compose-ssh@main
      name: Docker-Compose Remote Deployment
      with:
        ssh_host: example.com
        ssh_private_key: ${{ secrets.EXAMPLE_COM_SSH_PRIVATE_KEY }}
        ssh_user: ${{ secrets.EXAMPLE_COM_SSH_USER }}
        docker_compose_prefix: example_com
```
