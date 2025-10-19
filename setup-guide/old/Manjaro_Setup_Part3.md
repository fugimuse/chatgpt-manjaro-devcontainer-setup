## 🖥️ Phase 6: X11 Configuration
> **Goal:** Switch GNOME to use X11 instead of Wayland for stability on older Mac Mini hardware.

### 6.1 Configure X11 as Default Session
```bash
sudo cp /etc/gdm/custom.conf /etc/gdm/custom.conf.orig
sudo nvim /etc/gdm/custom.conf
# Add or uncomment under [daemon]:
WaylandEnable=false
sudo systemctl restart gdm
```

### 6.2 Verify X11 Session
```bash
echo $XDG_SESSION_TYPE  # should output x11
loginctl show-session $(loginctl | grep $(whoami) | awk '{print $1}') -p Type
```

### 6.3 Display Configuration
```bash
sudo pacman -S xorg-xrandr arandr
xrandr --output HDMI-1 --mode 1280x720 --rate 60
```
> 💡 Use `arandr` GUI to save display layouts persistently.

---

## 🎨 Phase 7: GNOME Theming
> **Goal:** Apply Dracula and TokyoNight themes for a consistent desktop look.

### 7.1 Install Dracula Theme
```bash
git clone https://github.com/dracula/gtk.git
sudo cp -r gtk/Dracula /usr/share/themes/
sudo cp -r gtk/Dracula /usr/share/icons/
yay -S dracula-cursors-git
```

### 7.2 Install TokyoNight Theme (Optional)
```bash
yay -S tokyonight-gtk-theme-git
```

### 7.3 Apply Themes
```bash
gsettings set org.gnome.desktop.interface gtk-theme 'Dracula'
gsettings set org.gnome.desktop.interface icon-theme 'Dracula'
gsettings set org.gnome.desktop.interface cursor-theme 'Dracula-cursors'
```
> 🎨 Or use **GNOME Tweaks** for easier switching between themes.

---

## 🧰 Phase 8: Development Tools Installation
> **Goal:** Install programming language managers and development toolchains.

### 8.1 Install ASDF Version Manager
```bash
pamac install asdf-vm
echo '. /opt/asdf-vm/asdf.sh' >> ~/.config/zsh/.zshrc
exec $SHELL
```

### 8.2 Install Programming Languages via ASDF

#### Python
```bash
asdf plugin add python
asdf install python latest
asdf set -u python latest
```

#### Node.js and Deno
```bash
asdf plugin add nodejs
asdf plugin add deno
asdf plugin add bun
asdf install nodejs latest
asdf install deno latest
asdf install bun latest
asdf set -u nodejs latest
asdf set -u deno latest
asdf set -u bun latest
```

#### Haskell
```bash
asdf plugin add haskell
asdf install haskell 9.10.3
asdf set -u haskell 9.10.3
```

#### Elixir and Erlang
```bash
asdf plugin add erlang
asdf plugin add elixir
asdf install erlang latest
asdf install elixir latest
asdf set -u erlang latest
asdf set -u elixir latest
```

#### Ruby and Perl
```bash
asdf plugin add ruby
asdf install ruby latest
asdf set -u ruby latest

asdf plugin add perl
asdf install perl latest
asdf set -u perl latest
```

#### Java, Kotlin, and Scala
```bash
asdf plugin add java
asdf plugin add kotlin
asdf plugin add scala
asdf install java latest
asdf install kotlin latest
asdf install scala latest
asdf set -u java latest
asdf set -u kotlin latest
asdf set -u scala latest
```

### 8.3 Install Go and Rust
```bash
sudo pacman -S go
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source ~/.cargo/env
```
> 🧩 Go and Rust are installed via their native tools for best compatibility.
