# AWS Organizations
Po založení root účtu v AWS je vhodné definovat organizaci.  
Zde se pak dá nastavovat:
- SCP (Service Control Policy): Tj. Např. omezit AWS na určitý region.
- Tag Policies: Zadat, jaké tagy se mají povinně vytvářet.

## Základní info k Organizitions
- Definovat v "root account"
- AWS Organizations - zdarma
- Organizace nemá žádné jméno, pouze ID. Jméno se dá volitelně definovat přes tagy.

## Jak na to: AWS Organizations
- Kde najdu: Vpravo nahoře rozbalítko na účtu: Organization
- Create an orgranization

## Vytvoření policy

### Nastavení: Tag Policies
- Policies
- Tag policies
- Enable Tag Policies
- Create Policy
- Vytvořit politiku

### Nastavení: SCP (Service Control Policy)
Pozn: Existuje defaultní politika "FullAWSAccess", která povoluje přístup do všeho. Když vytvořím svou vlastní omezující politiku, tak s touto nic dělat nemusím, protože: Omezující SCP převažuje, protože SCP Deny má přednost před Allow.
- Policies
- Service Control Policy
- Enable service control policies
- Create Policy
- Vytvořit politiku

## Přiřazení policy
- Vybrat politiku - Actions - Attach policy
- Vybrat, k čemu politiku přiřadím: obecně k root.

## Co dál
Dá se vytvořit consolidated billing
   - Musí být více uživatelů
   - Znamená to, že účtování bude souhrnné pro všechny účty, ne pro každý účet separé.
   - Mě se to nastavit nepodařilo, protože jsem consolidated billling nenašel
