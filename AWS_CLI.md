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

### Setup 1 - vytvoření: Access key
Jako vždy AWS doporučuje "IAM Identity Center" a ja jako vždy použil "IAM user". IAM user vhodný pro " user long-term credentials". Pro mé domáci použití stačí.
- Mám vytvořeného uživatele s policy: AdministratorAccess
- Toto je asi nejvyšší policy. (není třeba)
- IAM - Security credentials - Access key - Create access key
- Step 1: Command Line Interface (CLI), plus zatrhnout confirmation
- Step 2: nic
- Step 3: Download .csv file
- Done
- Pozn. Vygeneroval se: Access key ID, Secret access key

### Setup 2 - konfigurace AWS CLI
- cmd (normální uživatel)
- aws configure
```
C:\Users\karel.paulik>aws configure
AWS Access Key ID [None]: AKIATZLGYKJCYRJPTMBN
AWS Secret Access Key [None]: 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
Default region name [None]: eu-central-1
Default output format [None]: json
```
Toto nastavení se ve win uloží do souborů: 
C:\Users\karel.paulik\.aws\
- config
- credentials
Pozn: Tyto dva soubory můžu použít, kdybych se chtěl připojovat na AWS CLI na jiném PC. Prostě jen zkopírovat tyto soubory a vložit do správné složky.

### Použití AWS CLI
- aws s3 ls
- aws lightsail get-instances
- aws ec2 describe-instances
