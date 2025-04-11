### Jak funguje Amplify API pod pokličkou

1.  **Definice a vytvoření tabulek v DynamoDB:**
    * **Amplify (CLI)** na základě vaší definice datového modelu (pomocí direktivy `@model` ve `schema.graphql`) generuje šablony pro **AWS CloudFormation**.
    * **AWS CloudFormation** pak na základě těchto šablon **řídí vytvoření a konfiguraci** samotných DynamoDB tabulek ve vašem AWS účtu.

2.  **Zpracování dotazů na API:**
    * Když vaše aplikace odešle GraphQL dotaz na váš API endpoint, tento požadavek směřuje na **AWS AppSync**.
    * **AWS AppSync** tento dotaz přijme a na základě definovaného schématu a **resolverů** určí, jak má být dotaz zpracován a odkud se mají data načíst.
    * Pro dotazy, které se týkají dat uložených v DynamoDB (a mají nakonfigurované DynamoDB resolvery), **AppSync provede potřebné operace na těchto DynamoDB tabulkách** (např. `GetItem`, `Query`).

3.  **Vracení výsledků dotazu:**
    * **Ano, výsledky dotazu vrací zpět klientovi opět AWS AppSync.**
    * AppSync obdrží data z vašeho zdroje dat (v tomto případě DynamoDB) na základě provedených operací definovaných v resolveru.
    * Tyto data pak **transformuje do formátu odpovídající struktuře požadované ve vašem GraphQL dotazu** a odešle je jako odpověď zpět vaší aplikaci.

**Shrnutí celého toku:**

* **Vývojář definuje API a data v Amplify.**
* **Amplify "řekne" CloudFormation, jak má vypadat infrastruktura (včetně DynamoDB a AppSync).**
* **CloudFormation vytvoří a nakonfiguruje tuto infrastrukturu v AWS.**
* **Klient posílá GraphQL dotazy na AppSync.**
* **AppSync pomocí resolverů komunikuje s DynamoDB (a dalšími zdroji dat).**
* **AppSync vrací klientovi výsledky ve formátu GraphQL.**

