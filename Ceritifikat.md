# Vytvoření certifikátu pro domény
1. Certificate Manager
2. Request certificate
3. Request public certificate
4. - Zadat domény
   - Validation method: DNS Validation
   - Key algorithm: RSA 2048
5. Odeeslat request (toto samotné nestačí)
6. List certificate - kliknout na certifikát
7. - Domains - zde vidím domény, u nich "Pending validation"
   - Domains - (Domény jsou vybrány) Create records in Route 53 - Crete records
   - Bez tohoto kroku zůstane viset u certifikátu "Pending Validation"
8. Status certifikátu se změní: Pending validation -> Issued (Cerrtifikát vystaven)

## Validation method
1. DNS Validation
   - V tomto případě musím po odeslání requestu provést další kroky pro doménu: Přidat záznamy CNAME.
3. Email validation
   - Zde by měl přijít validační email.
