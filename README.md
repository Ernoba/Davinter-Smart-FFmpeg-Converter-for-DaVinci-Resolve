# 🎬 Davinter — Smart FFmpeg Converter for DaVinci Resolve

---

## 💡 Overview
**Davinter** (short for *DaVinci Converter*) is a smart Bash-based automation tool built to **make any video fully compatible with DaVinci Resolve**, especially on Linux.  

It was born from the universal pain of every editor screaming:  
> “Why won’t Resolve open my video when VLC plays it perfectly?!” 😤  

Davinter automatically detects and converts unsupported footage into **ProRes HQ** (or DNxHR) using professional-grade settings — ensuring your files are crisp, color-accurate, and fully ready for DaVinci.

---

## ⚙️ Key Features
✅ **Auto Codec Detection**  
Intelligently checks both video and audio codecs, converting only what’s necessary. Files already compatible are skipped automatically.  

✅ **ProRes HQ Output**  
Uses `prores_ks` encoder with 10-bit `yuv422p10le` pixel format — the industry-standard setup for high-end editing pipelines.  

✅ **Parallel Conversion (Multi-Core Power)**  
Runs multiple conversions simultaneously using `xargs -P`, fully utilizing your CPU cores for faster batch processing.  

✅ **Per-File Logging System**  
Each file has its own detailed log in `davinter_logs`, making debugging simple and organized.  

✅ **Auto Dependency Checker**  
If `ffmpeg` or `ffprobe` aren’t installed, Davinter automatically provides OS-specific installation instructions (Ubuntu, Fedora, Arch, macOS, etc).  

✅ **Dry-Run Mode (Simulation)**  
Preview the conversion process without touching any file — perfect for testing or verifying before running real jobs.  

✅ **Smart File Naming**  
Converted files are saved with a `_davinci.mov` suffix, preserving your original footage and keeping outputs clean and sorted.  

---

## 🧠 How It Works
1. Scans your input directory for all video files.  
2. Uses `ffprobe` to detect codecs.  
3. Converts only incompatible files into **ProRes HQ (MOV)**.  
4. Logs each process separately in the `davinter_logs` directory.  
5. Produces high-quality, DaVinci-ready videos with no “Media Offline” issues.  

---

## Instalation
download file davinter.
```bash
chmod +x davinter
sudo mv davinter /usr/local/bin
```


## 🧰 Example Usage

```bash
# Basic usage
davinter ./videos ./converted 8

# Dry-run (simulate without converting)
davinter --dry-run ./footage ./output

# Show installation help
davinter --install-deps
