# Nastavení přístupových práv

## Jak přiřadit **Cost and usage** práva jinému uživateli než je root
1. Defaultně může provádět jen root (bez ohledu na přiřazené policy). Pokud chceme přidat jinému uživateli nutno:
- Root account
- Vpravo nahoře: jmeno.prijmeni - account
- IAM user and role access to Billing information - Edit
- Activate IAM Access
- Update

2. Nyní možno přiřadit práva "cost and usage" jiným uživatelům
- **IAM policy**
- AdministratorAccess - toto je nejsilnější účet, takže uživatel s touto policy má přístup do "cost and usage" (za splnění podmínky ad.1).

**Pozn:** AdministratorAccess je asi nejsilnější policy.

## Politiky užitečné pro admina, když se nechce použít "AdministratorAccess"
- AWSBillingReadOnlyAccess: Poskytuje přístup pouze pro čtení k Billing and Cost Management konzoli. To zahrnuje prohlížení nákladů, faktur a Cost Exploreru.
- AWSBudgetsReadOnlyAccess: Poskytuje přístup pouze pro čtení k AWS Budgets, což může být užitečné pro sledování nákladů oproti definovaným rozpočtům.
