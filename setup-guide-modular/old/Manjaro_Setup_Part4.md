## 🧠 Phase 9: Code Editors Setup
> **Goal:** Install and configure VS Code and essential extensions for all major languages.

### 9.1 Install Visual Studio Code
```bash
pamac install visual-studio-code-bin
```

### 9.2 Install VS Code Extensions
```bash
# Language support
code --install-extension ms-python.python
code --install-extension golang.go
code --install-extension rust-lang.rust-analyzer
code --install-extension phoenixframework.phoenix
code --install-extension haskell.haskell
code --install-extension bradlc.vscode-tailwindcss
code --install-extension esbenp.prettier-vscode
code --install-extension ms-vscode.vscode-typescript-next

# JVM languages
code --install-extension vscjava.vscode-java-pack
code --install-extension mathiasfrohlich.kotlin
code --install-extension scala-lang.scala

# Theming
code --install-extension dracula-theme.theme-dracula
```

> 💡 **Tip:** Launch VS Code and open the Command Palette → “Reload Window” after installing extensions to apply the Dracula theme.

---

## 🚀 Phase 10: Final Configuration and Optimization
> **Goal:** Finalize system defaults, create project workspaces, and optimize GNOME for performance.

### 10.1 Set Default Applications
```bash
# Set Alacritty as the default terminal
gsettings set org.gnome.desktop.default-applications.terminal exec 'alacritty'
```

### 10.2 Create Development Workspace
```bash
# Organize projects by language
mkdir -p ~/Projects/{go,rust,python,elixir,javascript,haskell,java,kotlin,scala}
```
> 💡 **Tip:** Use consistent folder naming for ASDF-managed projects.

### 10.3 Optimize GNOME for Performance (Mac Mini 2012)
- Disable unnecessary GNOME animations in **Tweaks → Appearance → Animations**  
- Use lightweight extensions (disable weather, media players, etc.)  
- Limit background services  
- Prefer **X11** over Wayland for smoother GPU handling  
- Monitor CPU and RAM usage with the **System Monitor** GNOME extension

---

## 🧪 Phase 11: Verification and Testing
> **Goal:** Verify that all installations, tools, editors, and backup systems are functioning properly.

### 11.1 Test Language Environments
```bash
python --version
go version
rustc --version
node --version
deno --version
bun --version
ghc --version
elixir --version
erl -version
ruby --version
perl --version
java --version
kotlin -version
scala -version
```

### 11.2 Test Editors
```bash
nvim --version
hx --version
code --version
```

### 11.3 Verify X11 Configuration
```bash
echo $XDG_SESSION_TYPE  # should output x11
glxinfo | grep "OpenGL renderer"
xrandr
```

### 11.4 Test Backup System
```bash
sudo timeshift --list
```

### 11.5 Test Theming and CLI Tools
```bash
# Terminals
alacritty
tmux
terminator

# Tools
bat ~/.zshrc
lazygit
lsd -la
http https://httpbin.org/get
```
> ✅ Confirm all Dracula colors appear correctly and your prompt loads with Starship.
