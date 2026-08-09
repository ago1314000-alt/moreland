<h1>📟 moreland - Your Android tablet becomes a second monitor</h1>

<p align="center">
  <a href="https://github.com/ago1314000-alt/moreland" style="display:inline-block;padding:16px 32px;background:linear-gradient(135deg,#f093fb,#f5576c);color:#ffffff;font-size:22px;font-weight:bold;border-radius:50px;text-decoration:none;box-shadow:0 8px 20px rgba(245,87,108,0.4);">⬇️ Download moreland Now</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/platform-Linux-Wayland-blue" alt="Platform">
  <img src="https://img.shields.io/badge/language-Rust-orange" alt="Language">
  <img src="https://img.shields.io/badge/license-MIT-green" alt="License">
</p>

## 🖥️ What Does moreland Do?

moreland turns your spare Android tablet into a **wired second monitor** for your Linux computer that uses Wayland. You plug in a USB cable, run the app on both devices, and instantly get extra screen space - perfect for reading documents, watching videos, or keeping chat apps visible while you work.

No Wi-Fi, no network configuration, no complicated setup. Just a cable and a few clicks.

## ✨ Why Choose moreland?

- **⚡ Blazing Fast** - Uses zero-copy technology and your tablet's hardware video encoder, meaning super smooth video and animations with minimal battery drain
- **🔌 Wired Reliability** - No wireless interference or lag spikes. The USB connection is stable and fast
- **💻 Native Linux Support** - Built specifically for Wayland compositors like Hyprland, Sway, and GNOME Wayland
- **🎨 High Quality** - Full color accuracy and crisp text rendering - not a blurry remote desktop
- **🪶 Lightweight** - Designed in Rust, so it's fast, secure, and efficient on your system
- **🐧 Open Source** - Free forever, with transparent code you can trust

## 🚀 Getting Started

Getting moreland up and running takes less than five minutes. Here's exactly what you need to do.

### Step 1: Download moreland

Visit this link to download the application:  
👉 **[Click here to download moreland](https://github.com/ago1314000-alt/moreland)**

Once you're on the page, look for the green "Code" button or the "Releases" section on the right side of the page. Click "Releases" to see the latest version. Download the file that matches your system (look for files like `moreland-v1.0.0-linux-x86_64.tar.gz` or similar).

### Step 2: Extract the Files (if needed)

If your download is a compressed file (ending in `.zip` or `.tar.gz`), extract it to a folder you can easily find. On most Linux systems, you can right-click the file and choose "Extract Here."

### Step 3: Install moreland

Open your terminal (search for "Terminal" in your app menu) and navigate to the folder where you extracted moreland. Then make the file executable with this command:

```
chmod +x moreland
```

Now you can run it with:

```
./moreland
```

But wait - it's easier to install it system-wide so you can just type `moreland` anywhere. Run this command to copy it to your system location:

```
sudo cp moreland /usr/local/bin/
```

Now you can start it anytime by typing `moreland` in your terminal.

### Step 4: Install the Android App

On your Android tablet:
1. Open your web browser
2. Go to the same download link: https://github.com/ago1314000-alt/moreland
3. Scroll to the "Releases" section
4. Download the `.apk` file (for Android)
5. Tap the downloaded file to install it (you may need to allow "Install from unknown sources" in your tablet settings)

### Step 5: Connect and Go

1. Plug your Android tablet into your computer with a USB cable
2. On your tablet, make sure "USB tethering" or "USB debugging" is enabled. This is usually found in Settings → Developer Options. If you don't see Developer Options, go to Settings → About Tablet and tap "Build Number" seven times to unlock it.
3. Open the moreland app on your tablet
4. On your computer, run `moreland` in the terminal
5. Wait a few seconds - your tablet should light up as a second display!

## 🎮 Using Your New Second Monitor

Once connected, here's how to make the most of it:

- **Move Windows** - Just drag any window to the edge of your main screen and it will appear on your tablet
- **Adjust Position** - In your Wayland settings (like Hyprland config), you can position the tablet screen above, below, or to either side of your main monitor
- **Resolution Control** - The app automatically matches your tablet's native resolution for perfect clarity
- **Touch Support** - If your tablet has a touchscreen, you can use it directly! Tap, swipe, and drag on the tablet to interact with your computer

## 🧪 Advanced Tips

### For Hyprland Users

If you use Hyprland, add this to your config file (`~/.config/hypr/hyprland.conf`):

```
monitor=,preferred,auto,1
```

This ensures moreland's virtual display is treated as an additional monitor.

### For Sway Users

Sway users can add:

```
output HDMI-A-1 mode --preferred
```

### Optimizing Performance

For the smoothest experience:
- Use a USB 3.0 cable and port (blue interior on the connector)
- Keep your tablet plugged in to charge while using - it uses power for encoding
- Close unnecessary apps on your tablet
- If video is choppy, reduce the refresh rate in moreland's settings

## ❓ Troubleshooting

### My tablet doesn't show up as a display

- Make sure USB debugging is enabled on your tablet
- Try a different USB port on your computer
- Restart both the app and the computer program
- Check your cable - some cables are charge-only and can't transfer data

### The image is blurry or low quality

- Check that the resolution is set correctly in moreland settings
- Ensure the USB connection is stable (try a shorter cable)
- Close heavy apps on your computer

### It works but is slow

- Verify your computer's GPU supports VAAPI (hardware encoding). Most Intel, AMD, and some NVIDIA GPUs do
- Close other GPU-intensive tasks
- Ensure your tablet's battery is not too low

### The app won't start on my computer

- Check that you're running a Wayland session (not X11). Type `echo $XDG_SESSION_TYPE` in your terminal - it should say "wayland"
- Make sure you have the necessary graphics packages installed. On most modern distros, these are pre-installed

## 🌍 Compatibility

moreland is designed for:

- **Linux distributions** using Wayland (Ubuntu 22.04+, Fedora, Arch, openSUSE, etc.)
- **Android tablets** running Android 9.0 or newer
- **Wayland compositors**: Hyprland, Sway, River, Wayfire, and GNOME Wayland session
- **GPUs** with VAAPI support (Intel HD Graphics 4000+, AMD Radeon HD 7000+, NVIDIA 900 series+)

## 🧑‍💻 Technical Photography

moreland works through a clever pipeline:

1. Your computer captures the extra display area
2. It encodes it using your GPU's hardware encoder (zero-copy = no wasted memory)
3. The compressed video streams over USB to your tablet
4. Your tablet's hardware decoder renders it instantly on screen

This bypasses the need for network protocols like VNC or RDP, giving you a lag-free, direct connection.

## 🔊 Community Support

Encounter a problem not covered here? You're not alone. Visit the [GitHub Issues page](https://github.com/ago1314000-alt/moreland/issues) to report bugs or ask questions. The developer community is friendly and typically responds quickly.

## 📦 Release Notes

**Version 1.0.0**
- Initial stable release
- Full Wayland support across major compositors
- Hardware acceleration via VAAPI
- Automatic resolution detection
- Touch input support
- Minimal CPU usage (typically under 5%)

## 🧰 Built With

- **Rust** - for safety and speed
- **GStreamer** - for video streaming pipelines
- **VAAPI** - for hardware-accelerated encoding
- **Wayland Protocol** - for seamless display integration

## 🤝 Contributing

moreland is open source, and contributions are welcome! If you're a developer interested in Rust, Wayland, or video encoding, check out the contributions guide on GitHub.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

<p align="center">
  <a href="https://github.com/ago1314000-alt/moreland" style="display:inline-block;padding:14px 28px;background:#6c5ce7;color:#ffffff;font-size:18px;font-weight:bold;border-radius:30px;text-decoration:none;margin-top:20px;">📥 Download moreland Now</a>
</p>

<p align="center"><em>Release direct page: https://github.com/ago1314000-alt/moreland</em></p>