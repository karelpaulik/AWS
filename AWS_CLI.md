### Stažení inst. balíčku
https://awscli.amazonaws.com/AWSCLIV2.msi

### Spuštění instalace
- Spustit instalátor (spouštěl jsem jako obyč. uživatel)
- Ponechal jsem cestu zvolenou instalátorem: C:\Program Files\Amazon\AWSCLIV2\
- Požadavek na místo: 174 MB
- Instalátor si vyžádal admin. účet
- Čas instalace: cca 1 min.

### Pozn.
Někde jsem četl, že AWS CLI potřebuje nainstalovaný python. Ten jsem měl již z dřívějška nainstalovaný, jestli je potřeba nebo ne nevím. Ale v AWS dokumentaci o tom nepsali.

### Kontrola instalace
- aws --version
- Výsledek: aws-cli/2.25.12 Python/3.12.9 Windows/10 exe/AMD64

### Po instalaci
Možno smazat instalační balíček

### Setup
Jako vždy AWS doporučuje "IAM Identity Center" a ja jako vždy použil "IAM user". IAM user vhodný pro " user long-term credentials". Pro mé domáci použití stačí.
- Mám vytvořeného uživatele s policy: AdministratorAccess
- Toto je asi nejvyšší policy. (není třeba)
