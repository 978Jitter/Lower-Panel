## // Customizing the Lower XFCE Panel Background

If the default GTK/theme styling on the lower dock/panel doesn't match your layout, override it directly in XFCE Panel Preferences with a custom `.png` background image.

### 1. GUI Method (Panel Preferences)
1. **Open Panel Preferences:** Right-click an empty spot on the lower panel (or press `Alt+F2` / run `xfce4-panel --preferences` in terminal) and select **Panel → Panel Preferences…**.
2. **Select the Lower Panel:** At the very top of the window, use the **Panel** dropdown (`Panel 1`, `Panel 2`, etc.) to select your lower panel (a red outline will highlight the active panel on screen).
3. **Open the Appearance Tab:** Click the **Appearance** tab.
4. **Set Background Style to Image:** Under the **Background** section, change **Style** from `None (use system style)` to **`Background image`**.
5. **Aim It at Your `.png`:** Click the **Image** file selector button, browse to your custom panel `.png` file (for example, inside `extras/` or `~/.themes/Jitter-Shadow/panel/`), and click **Open**.
6. **Close:** Click **Close**—the lower panel updates immediately.

### 2. Terminal One-Liner (`xfconf-query`)
You can also set the lower panel background directly from the terminal (replace `panel-2` with your lower panel's ID if needed, and update the path to your `.png`):

```bash
xfconf-query -c xfce4-panel -p /panels/panel-2/background-style -n -t int -s 2
xfconf-query -c xfce4-panel -p /panels/panel-2/background-image -n -t string -s "$HOME/path/to/your-panel-bg.png"
xfce4-panel -r
