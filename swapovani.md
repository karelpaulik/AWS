# Lightsail nemá defaultně povoleno swapování.

Je vhodné swapování nastavit. Pro lightsail 1GB RAM, 40GB HDD tak 4-8 GB.

free -m  # Kolik je volné RAM, po nastaveni swapu: Kontrola, že swap funguje.
df -h    # Kolik je volného místa na disku

## Jak nastavit svapování
- Vytvoření swap souboru
- Nastavení oprávnění
- Formátuj jako swap
- Aktivuj swap
- Ověř, že swap funguje.
- Ověření, že swap file byl vytvořen se správnou velikostí a se správným oprávněním. (Vhodné (ale ne nutné) po vytvoření souboru a dále po nastavení oprávnění pro kontrolu.)

```
sudo fallocate -l 1G /swapfile	
sudo chmod 600 /swapfile		
sudo mkswap /swapfile			
sudo swapon /swapfile			
free -m
ls -lh /swapfile					
```

## Zvětšení existujícího swap. souboru:
Nutno smazat starý a nastavit nový. Jak:

- Vypni stávající swap
- Smaž starý swap soubor

```
sudo swapoff /swapfile
sudo rm /swapfile
```
