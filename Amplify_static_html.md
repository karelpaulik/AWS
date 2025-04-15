# Hostování stat. html přes amplify - dvě možnosti

### 1. Ručně přes zip soubor
Vytvořit zip soubor, kde bude index.html v rootu. Tzn. nebalit složku, kde jsou soubory, ale přímo soubory (případně podadresáře).

### 2. Amplify cli
- **amplify init**
- **amplify add hosting**
- -- Zde je možno: Buď hosting přes amplify, nebo přes Amazon Cloudfront and S3
- -- !!! Pouze v možnosti "Amazon Cloudfront and S3", najdu zdorojové soubory na cloudu, tj. v S3 bucketu.
- -- V tomto případě se vytvoří dva buckety: 1. deployment, 2. hosting (tento se vytvořil se zpožděním. cca 10min)
- **amplify publish**
- -- Tímto se web nasadí, ale soubory na AWS nenajdu (přes Amazon Cloudfront and S3 najdu, ale není to standartní řešení)
- Dále při chybách potřebuji:
- **amplify configure project**
- --Project information
- -- Source directory path: .
- -- Distribution Directory Path: .
- -- Build command: echo "b"  (něco co nic nedělá)
- -- Start command: echo "s"  (něco co nic nedělá)

## !!! Pozor - u obou těchto možností nemám možnost se dostat z Amplify, ke zdrojovým souborům
## !!! Pozor - amplify pull: stahuje pouze backend, ne frontend
Tzn. že front end mám buď na github, nebo lokálně. 

## Po úpravě např. index.html
- amplify publish

# Shrnutí Amplify cli
```
amplify init
amplify add hosting
amplify publish
     PO ÚPRAVĚ
amplify publish
     PŘI PROBLÉMECH
amplify configure project
```
