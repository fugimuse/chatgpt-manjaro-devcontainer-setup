# DevPod + Podman DevContainer Templates (Server‑Side Languages + Frontend Tooling)

This repository contains **DevPod** templates based on **devcontainer.json** and **Containerfile** (Podman-friendly) for major server-side languages.
Each template includes **Node.js** and popular frontend tooling (npm, pnpm, yarn, vite, sass, eslint, prettier) so you get a full‑stack environment in one container.

## Quick start

1. **Install prerequisites**
   - Podman (rootless recommended)
   - DevPod CLI (`curl -fsSL https://get.devpod.sh | sh`)
   - VS Code or any editor that understands Dev Containers (optional)

2. **Clone or unzip templates**
   - Download the ZIP from this chat, unzip somewhere (e.g., `~/devpod-templates`).

3. **Create a workspace using DevPod with Podman**
   ```bash
   devpod up --id my-<language> --provider podman ./<language>
   ```
   Replace `<language>` with one of the template folders (e.g., `python`, `go`, `java`, etc.).

4. **Attach your editor**
   - If using VS Code with the Dev Containers extension, open the folder and it should auto‑detect `devcontainer.json`.
   - Or use `devpod ssh my-<language>` to drop into the container and run your tools.

## Templates included

- `node` (Node.js runtime for server-side JS/TS)
- `python` (3.12)
- `go` (1.23)
- `java` (OpenJDK 21)
- `dotnet` (.NET 8 SDK)
- `ruby` (3.3)
- `php` (8.3 CLI; add web server as needed)
- `rust` (stable + rustup)
- `elixir` (Erlang/OTP + Elixir)
- `deno` (latest)

Each template provides:
- Linux base (Debian/Ubuntu or official upstream image)
- Node.js LTS + npm, pnpm, yarn
- Frontend tools: vite, sass, eslint, prettier
- Git, curl, bash nano/vim basics
- Non‑root `dev` user (UID:GID 1000) with passwordless sudo
- `devcontainer.json` set up for DevPod / Podman

> Tip: For per‑project ports, volumes, or environment variables, edit the `devcontainer.json` in the chosen template.

## Podman notes

- These templates use a `Containerfile` rather than `Dockerfile`, but DevPod accepts either.
- If you prefer Docker, simply rename `Containerfile` to `Dockerfile` and switch DevPod provider to Docker.

## Adding frontend frameworks

Because Node.js is installed in every image, you can run:
```bash
pnpm create vite@latest
# or
npm create next-app@latest
# or
yarn create react-app myapp
```

## Customizing images

- Add OS packages in the `apt-get install` lines.
- Add language‑specific tools (linters, formatters, debuggers) as needed.
- Mount host directories or secrets via `mounts` / `remoteEnv` in `devcontainer.json`.

---

> Created for: Adapted Manjaro setup into isolated DevPod+Podman dev containers for each major language.
