### Domény - Route 53
AWS neumí registovat **.eu** domény. Ale umí tyto domény spravovat. Tzn. že můžu mít doménu **xxx.eu** registrovanou např. u forpsi, a tady ji spravovat.

AWS umí velice rychle spravovat domény v **Route53**. Když upravím svázání s IP adresou (např. Lightsail), tak během okamžiku cca 1 minuty vidím na webu pod doménou novou IP adresu.

### Certifikáty - Certificate manager
Když chci k doméně (která je registrovaná jinde než u AWS) vygenerovat certifikát, tak to trvá pěkně dlouho, zřejmě se čeká na nějaké ověření od registrátora.
