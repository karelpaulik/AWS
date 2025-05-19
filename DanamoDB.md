# DynamoDB
Nevýhody:
- Neumí pracovat s databázemi.
  - Tzn. Všechny tabulky nacpe do DynamoDB a pro účely testování není možnost zkopírovat celou databázi. Doporučení je zkopírování tabulky s jejím přejmenováním. Např. User .. test_User. Což v případě celých aplikací by znamenalo přepsat reference na nové tabulky.
