# 📊 Systemmonitoring PowerShell-Paket

Dieses PowerShell-Skriptpaket dient zur kontinuierlichen Überwachung von Systemressourcen unter Windows und erzeugt strukturierte Logdateien bei Überschreitung konfigurierbarer Schwellenwerte.

---

## 🔧 Funktionen

- ✅ Überwachung von CPU- und RAM-Auslastung pro Prozess
- ✅ Logging bei hoher Handle- oder Threadanzahl
- ✅ Schwellenwerte frei konfigurierbar (`config.json`)
- ✅ Logging in TXT **und** CSV
- ✅ Getrennte Logdateien für CPU- und Netzwerkaktivitäten
- ✅ Optionale tägliche Log-Archivierung als ZIP
- ✅ Optional: Benachrichtigung per **E-Mail**, **Teams**, **Telegram**

---

## ⚙️ Einrichtung

1. 📂 Entpacke das ZIP in ein Verzeichnis, z. B. `C:\Monitoring`
2. 📝 Bearbeite `config.json` nach deinen Anforderungen:
   ```json
   "cpuThreshold": 50,
   "ramThresholdPercent": 50,
   "handleThreshold": 10000,
   "threadThreshold": 200
   ```
3. ▶ Starte das Skript:
   ```powershell
   .\Monitor.ps1
   ```

---

## 📁 Ausgabe

- TXT-Log pro Tag:
  - `cpu_monitor_YYYYMMDD.txt`
  - `net_monitor_YYYYMMDD.txt`
- CSV-Log pro Tag:
  - `cpu_monitor_YYYYMMDD.csv`
- (optional) ZIP-Archiv:
  - `MonitorLogs_YYYYMMDD.zip`

---

## 📬 Benachrichtigungen (optional aktivierbar)

Konfiguriere in `config.json`:
```json
"emailEnabled": true,
"teamsEnabled": true,
"telegramEnabled": false
```

---

## 🛡️ Rechte / Voraussetzungen

- PowerShell 5.1 oder höher
- Lokale Ausführung von Skripten erlauben:
  ```powershell
  Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
  ```

---

## 🧪 Tipps

- Automatischer Start mit Windows: per `Taskplaner` (geplant)
- Prüfe regelmäßig den Logordner: `logPath` in `config.json`

---

© 2025 Denis Mau
