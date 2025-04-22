## Jak nastavit omezení uživatele, aby mohl pracovat pouze s jedním regionem.

---

### 🔧 Postup: Omezení přístupu uživatele pouze na 1 region (např. `eu-central-1`)

#### ✅ 1. Přihlas se do AWS Console

Přejdi na: **IAM > Users > [vybraný uživatel] > Permissions**

#### ✅ 2. Klikni na **“Add permissions”** > **“Add inline policy”**

Tím přidáš vlastní politiku, která se vztahuje pouze na tohoto uživatele.

#### ✅ 3. Vyber záložku **JSON** a vlož následující politiku:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "DenyAllOutsideRegion",
      "Effect": "Deny",
      "Action": "*",
      "Resource": "*",
      "Condition": {
        "StringNotEquals": {
          "aws:RequestedRegion": "eu-central-1"
        }
      }
    }
  ]
}
```

💬 Tahle politika:

- **Zakazuje všechny akce ve všech regionech kromě `eu-central-1`**.
- Funguje jako *“Deny override”*, tzn. i kdyby jiná politika něco povolovala, tahle to přebije mimo vybraný region.

#### ✅ 4. Klikni na **Review policy**, zadej jméno např. `LimitToEuCentral1` a klikni **Create policy**

---

### 🧪 Ověření

Můžeš přihlásit uživatele a zkusit:

- Spustit EC2 instanci v jiném regionu → mělo by to selhat (`AccessDenied`).
- Spustit EC2 v `eu-central-1` → mělo by to projít, pokud má jiná politika povolující tuto akci.

---

Chceš k tomu ještě CLI variantu nebo rozšíření např. o whitelist jen několika služeb?
