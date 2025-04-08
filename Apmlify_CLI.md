### Amplify CLI
Pokud chci používat Amplify CLI, je nutno ho ručně doinstalovat. Samotné AWS CLI nestačí. Tzn. mám nainstalované AWS CLI, doinstaluji "Amplify CLI" (v příkazovém pádku win) a pak můžu používat příkazový řádek pro amplify příkazy.
```
Ty se pak nebudou zadávat ve formátu:
"aws amplify ..."
ale ve formátu:
"apmlify ..."
```

### Kam nainstalovat
Lokálně ve svém cmd. (Může být i v cloudshell, ale to pak Pozor: CloudShell je dočasné, takže instalace zmizí po delší neaktivitě.)

### WIN - Cmd
```
npm install -g @aws-amplify/cli
amplify --version
```

### Konfigurace
Pokud je správně nakonfigurováno AWS CLI, není třeba nic dalšího konfigurovat.

### Příklady Použití
- amplify init
- npm install aws-amplify    (The aws-amplify package is the main library for working with Amplify Libraries in your projects)
- amplify add api
- amplify push

### Obvyklý postup v praxi
- amplify init → Vytvoří projekt a připraví AWS prostředí (jen metadata).
- amplify add <kategorie> (např. api, function) → Definuje zdroje lokálně.
- amplify push → Poprvé přesune část projektu (backend) na AWS.
