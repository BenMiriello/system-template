# Storage Schema

## Primary Storage

- **MacBook Air 1TB 🍏**
  - └─ Backed up by Time Machine 🕒 in **2TB External SSD 💿**
  - └─ Backed up by Manual Storage ✋🏻 in **2TB External SSD 💿**
  - └─ Connected to **iCloud ☁️**
  - [X] Mounts **Linux Machine 🐧** via Samba
    - [X] Via local connection automatically on startup
    - [X] Via tailnet connection automatically on startup when local connection fails

- **iPhone 16 Pro Max 512 GB 📱**
  - └─ Connected to **iCloud ☁️**

- **iCloud+ 2TB ☁️**
  - Photos Library (primary complete source of truth)
    - └─ Connected to **MacBook Air 🍏** Photos Library
    - └─ Connected to **iPhone 📱** Photos Library
    - └─ Backed up by **2TB External HDD 💾**
  - Messages
  - All Standard Apple Applications Data
  - Documents (including Development)
  - Raw Photos
  - iPhone and iPad Backups

- **Linux Machine (Debian) 🐧**
  - 3TB Total Internal SSD Storage
    - 2TB SSD - Primary storage
    - 1TB SSD - Extended file system
  - └─ Backed up by **4TB External HDD 💾💾**
  - [ ] Mounts **Macbook Air 🍏** via Samba
    - [X] Via local connection automatically on startup
    - [X] Via tailnet connection automatically on startup when local connection fails

## Backup Devices

- **4TB External HDD 💾💾**
  - 3TB **Linux Machine 🐧** Backup
  - 1TB Secondary **MacBook Air 🍏** Time Machine Backup
  - [ ] Automatically syncs when connected to Linux Machine

- **2TB External SSD 💿**
  - 1TB Time Machine 🕒 backup of **Macbook Air 🍏** (primary backup)
    - [ ] Automatically syncs to Macbook when connected to **Linux Machine 🐧**
  - 1TB Manual Storage ✋🏻 (All Raw Photos + other files)
    - [ ] Automatically syncs to **Macbook Air 🍏** when connected to **Linux Machine 🐧**
  - [ ] Safe unmounting from **Linux Machine 🐧** without use of interface

- **2TB External HDD 💾** (iCloud Mirror)
  - Full Backup of **iCloud ☁️**
  - [ ] Automatically syncs to **Macbook Air 🍏** when connected to **Linux Machine 🐧**
  - [ ] Safe unmounting from **Linux Machine 🐧** without use of interface
