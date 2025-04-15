# Hostování stat. html přes amplify - dvě možnosti

### 1. Ručně přes zip soubor

### 2. Amplify cli
- amplify init
- amplify add hosting
- amplify publish
- Dále při chybách potřebuji:
- amplify configure project
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
