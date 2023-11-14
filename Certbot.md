# Certbot Cheat Sheet

Certbot ist ein Tool zur Automatisierung des Erwerbs, der Verwaltung und der Erneuerung von SSL/TLS-Zertifikaten. Hier ist ein Cheat Sheet mit grundlegenden Befehlen und Optionen für Certbot:

## Installation von Certbot:

bash
Copy code
sudo apt-get update
sudo apt-get install certbot

## Zertifikat erstellen/erneuern:

bash
Copy code
# Erstelle oder erneuere Zertifikate für alle Domains in der Apache-Konfiguration
sudo certbot renew

# Interaktiver Modus zur Auswahl von Domains und Konfigurationsoptionen
sudo certbot --apache

# Erneuere alle Zertifikate ohne Interaktion (geeignet für Cron-Jobs)
sudo certbot renew --quiet

Erneuern und Konfiguration neu laden:
bash
Copy code
# Erneuere Zertifikate und lade Apache-Konfiguration neu
sudo certbot renew --quiet --post-hook "systemctl reload apache2"

# Neues Zertifikat
bash
sudo certbot --apache -d example.de

Zertifikat für spezifische Domänen erhalten:
bash
Copy code
sudo certbot certonly --apache -d example.com -d www.example.com
Automatische Weiterleitung von HTTP zu HTTPS:
bash
Copy code
# Aktiviere die automatische Weiterleitung in der Apache-Konfiguration
sudo certbot --apache
Manuelle Validierung mit Standalone-Modus:
bash
Copy code
# Stoppe den Apache-Server und starte den Standalone-Server für die Validierung
sudo systemctl stop apache2
sudo certbot certonly --standalone -d example.com
sudo systemctl start apache2
Automatische Aktualisierung von Nginx-Konfiguration:
bash
Copy code
# Aktualisiere die Nginx-Konfiguration automatisch
sudo certbot --nginx
Zertifikatinformationen anzeigen:
bash
Copy code
# Zeige Informationen zu einem bestimmten Zertifikat an
sudo certbot certificates
Testmodus (Dry Run):
bash
Copy code
# Teste den Certbot ohne tatsächliche Änderungen vorzunehmen
sudo certbot renew --dry-run
Automatischer Cron-Job hinzufügen:
bash
Copy code
# Füge einen täglichen Cron-Job für die automatische Erneuerung hinzu
sudo crontab -e
# Füge die Zeile hinzu:
0 0 * * * /usr/bin/certbot renew --quiet
Entfernen eines Zertifikats:
bash
Copy code
# Entferne ein Zertifikat und alle dazugehörigen Dateien
sudo certbot delete --cert-name example.com
Hilfe und Dokumentation:
bash
Copy code
# Zeige die allgemeine Hilfe an
certbot --help

# Zeige Hilfe für einen bestimmten Befehl an
certbot renew --help
