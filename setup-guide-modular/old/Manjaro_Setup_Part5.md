## 🩹 Troubleshooting
> **Goal:** Quickly diagnose and fix common setup issues.

### Common Issues and Fixes

- ⚠️ **ASDF not loading:**  
  Ensure your shell configuration sources the ASDF script.  
  ```bash
  echo '. /opt/asdf-vm/asdf.sh' >> ~/.zshrc
  exec $SHELL
  ```

- 🧱 **Fonts not displaying correctly:**  
  Rebuild the font cache and restart applications.  
  ```bash
  fc-cache -fv
  ```

- 💻 **Theme not applying:**  
  Ensure permissions are correct and restart the GNOME session.  
  ```bash
  gsettings set org.gnome.desktop.interface gtk-theme 'Dracula'
  gnome-shell --replace &
  ```

- 🔄 **X11 not active:**  
  Verify that Wayland is disabled in the GDM configuration and restart GDM.  
  ```bash
  sudo nvim /etc/gdm/custom.conf
  # Ensure WaylandEnable=false
  sudo systemctl restart gdm
  ```

- 🧰 **Starship not loading:**  
  Make sure the initialization line exists in your `.zshrc`.  
  ```bash
  eval "$(starship init zsh)"
  exec $SHELL
  ```

- 🧛 **Tmux plugins not loading:**  
  Open tmux and press `Ctrl+A` then `I` to install plugins manually.

- 💾 **Timeshift snapshots missing:**  
  Confirm Timeshift is configured for BTRFS and has enough free space.  
  ```bash
  sudo timeshift --list
  ```

> 💡 **Performance Tips for Mac Mini 2012:**  
> - Disable unnecessary GNOME animations  
> - Keep your background apps minimal  
> - Use X11 for smoother graphics  
> - Periodically clean up old Timeshift snapshots  

---

## 🏁 Next Steps
🎯 **Your Environment Is Ready!**

Now that your system is fully configured, here’s what you can do next:

1. **Customize your workflow**
   - Tune Neovim and Helix further to match your preferences  
   - Add language-specific LSP plugins via Lazy.nvim  

2. **Enhance backup reliability**
   - Plug in an external drive for redundant Timeshift backups  
   - Optionally, sync important folders to the cloud  

3. **Keep it beautiful**
   - Try other Dracula-compatible themes for apps like Obsidian and Firefox  
   - Add new GNOME extensions for productivity  

4. **Optimize and maintain**
   - Use `sudo pacman -Syu` weekly to stay up to date  
   - Verify Timeshift snapshots after major updates  
   - Clean up cached packages with `sudo paccache -r`  

5. **Explore more**
   - Add containerized dev environments (Podman, DevPod, or Docker)  
   - Configure Terraform, Go, and Rust projects with reproducible dev containers  

---

## ✅ Summary

You now have:

- A **fully themed Dracula environment** across GNOME, terminals, and editors  
- **ASDF-managed language runtimes** for all major stacks  
- **Automatic, snapshot-based backups** via Timeshift  
- **Optimized X11 graphics** for the 2012 Mac Mini  
- A **consistent developer experience** across all tools  

> 🧛‍♂️ Enjoy your sleek, powerful, and reliable **Manjaro GNOME Development Environment** — crafted for elegance, resilience, and creativity!
