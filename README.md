# drone_project

Starter Dockerized development workspace for keeping project installs inside a container.

## Requirements

- Docker Desktop
- VS Code with the Dev Containers extension

## Use With VS Code

1. Open this folder in VS Code.
2. Run `Dev Containers: Reopen in Container`.
3. Install project tools from the container terminal, not from Windows PowerShell.

## Use From A Terminal

```sh
docker compose up -d --build
docker compose exec dev bash
```

Inside the container, the project is mounted at:

```sh
/workspace
```

## Common Install Examples

Python:

```sh
python3 -m venv .venv
. .venv/bin/activate
pip install <package>
```

Node:

```sh
npm install <package>
```

The compose file stores `node_modules`, npm cache, and pip cache in Docker volumes so installs stay containerized and faster between rebuilds.
