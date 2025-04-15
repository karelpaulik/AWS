### Domény - Route 53
AWS neumí registovat **.eu** domény. Ale umí tyto domény spravovat. Tzn. že můžu mít doménu **xxx.eu** registrovanou např. u forpsi, a tady ji spravovat.

AWS umí velice rychle spravovat domény v **Route53**. Když upravím svázání s IP adresou (např. Lightsail), tak během okamžiku cca 1 minuty vidím na webu pod doménou novou IP adresu.

### Certifikáty - Certificate manager
Když chci k doméně (která je registrovaná jinde než u AWS) vygenerovat certifikát, tak to trvá pěkně dlouho, zřejmě se čeká na nějaké ověření od registrátora. Ještě jsem zkoušel, jestli já sám nemusím na webu registrátora (forpsi.com) něco provést, ale nic jsem nenašel.


# Zjištění informací k doméně:
## 1. who.is
- Zadat doménu
- Velice často je server přetížený, musel jsem zkoušet několikrát, než jsem dostal výsledek.

```
Domain: bedobe.eu
Script: LATIN

Registrant:
        NOT DISCLOSED!
        Visit www.eurid.eu for the web-based WHOIS.

Technical:
        Organisation: INTERNET CZ, a.s.
        Language: cs
        Email: 

Registrar:
        Name: INTERNET CZ, a.s.
        Website: www.forpsi.com/

Name servers:
        ns-1142.awsdns-14.org
        ns-951.awsdns-54.net
        ns-47.awsdns-05.com
        ns-1585.awsdns-06.co.uk

Please visit www.eurid.eu for more info.
```
Na základě WHOIS výsledku pro doménu **bedobe.eu**:

- **Vlastník (Registrant)**: Údaje o vlastníkovi nejsou zveřejněny („NOT DISCLOSED!“). To je běžné kvůli ochraně soukromí podle GDPR u evropských domén (.eu). Pro více informací navštívit web EURid (www.eurid.eu), kde zkusit podrobnější WHOIS dotaz.

- **Registrátor**: Doména je spravována společností **INTERNET CZ, a.s.** (FORPSI), českým poskytovatelem domén a hostingu. Můžete je kontaktovat přes jejich web (www.forpsi.com) nebo e-mail, pokud potřebujete zjistit více (např. přeposlání zprávy vlastníkovi).

- **Technické informace**:
  - **Organizace**: INTERNET CZ, a.s.
  - **Jazyk**: Čeština.
  - **E-mail**: Není uveden ve výstupu.

- **Jmenné servery (Name servers)**: Doména používá AWS DNS servery (**ns-*.awsdns-*.org/net/com/co.uk**), což naznačuje, že je pravděpodobně hostována nebo spravována přes **AWS Route 53**. To však přímo neprozrazuje vlastníka, pouze infrastrukturu.

### Shrnutí:
Vlastník domény **bedobe.eu** není veřejně uveden kvůli ochraně soukromí. Nejlepší krok je kontaktovat registrátora **INTERNET CZ, a.s.** (FORPSI) a požádat o zprostředkování kontaktu. Pokud jde o AWS certifikát, budete potřebovat přístup k DNS nastavení (Route 53) nebo souhlas vlastníka.

- **Vlastníka** jsem přes **www.eurid.eu** dohledal.

## 2. sysinternals - whois.exe
- Cmd
- Najet do adresáře, kde je **whois.exe**
- whois domena.eu

# Certifikáty ke statickým web. stránkám
Stat. html se dají na AWS hostovat několika způsoby. Ohledně SSL certifikátu se každý chová jinak.

## S3 stat. html - pro https je nutný předempřipravený SSL certifikát
- Zde se jednoduše vytvoří stat. html
- !!! S3 umí pouze **http**, neumí **https**
- Pro **https** je nutné hostování přes **CloudFront**
- **CloudFront** je možný pouze jako **https**
- **CloudFront** potřebuje vygenerovaný certifikát

## Stat. html přes amplify - pro https není nutný žádný SSL certifikát
- Jednoduché nahrání stránek přes zip (kde je v index.html v hl. úrovni), nebo přes *amplify cli*
- Amplify umí pouze **https**
- Při vytvoření stat. hostingu se vždy vygeneruje nějaký **https://xxx** endpoint, **bez toho, aby uživatel vkládal certifikát**
- **https** certifikát není potřeba, protože vygenerovaný endpoint je subdoména *amplify* a použije se certifikát od *amplify*.
- **Vlastní doména k amplify** - ani ta nepotřebuje můj SSL certifikát. I to běží automaticky.
