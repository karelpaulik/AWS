## AWS služby
- EC2
  - Load balancer
- Lightsail
- S3  (zde se dá nastavit: S3 Storage Lens - aby sledoval velikosti existujicích bucketů)
  - **StorageLens**
  - Pro přísup do StorageLens je potřeba nový uživatel s právy:
  - **Permissions required:**
  - s3:ListStorageLensConfigurations
  - s3:GetStorageLensConfiguration
  - s3:GetStorageLensDashboard
  - Pozn. Tyto práva nejsou v seznamu policy, ale je nutné vytvořit JSON s těmito právy.
- CloudFront
- Amplify
- AppSync  (GREAPHQL API)
- CloudFormation

- DynamoDB

- AWS Lambda
- Api Gateway  (REST api)

- AWS account
- AWS Organizations

- VPC
  - VPC
  - Subnets
  - Route tables
    - **Cílový blok vs Cílové umístění**
    - Cílový blok
      - Definuje rozsah IP adres, na které se dané směrovací pravidlo vztahuje.
      - 0.0.0.0/0 (internet)
      - 10.0.1.0/24
    - Cílové umístění
      - Určuje, kam má být síťový provoz směřován, pokud cílová IP adresa odpovídá cílovému bloku daného pravidla.
      - Může to být (existuje více než tyto 3, ale tyto jsou hlavní):
      - IGW
      - NAT
      - local (komunikace v rámci podsítě)
  - Internet gateway
  - NAT gateway
  - Elastic IP
  - Network ACL
  - Security groups
  

## Uživatelé
- IAM
  - User groups
  - Users
  - Roles
  - Policies
- IAM identity center

## Zabazpečení, logy, 
- CloudTrail (event history)
- CloudWatch (různé alarmy) - Billing alarm se vytváří v: Northern Virginia Region
- Trusted Advisor: Nenastavuje se, funguje automaticky od začátku existence AWS účtu. Když je něco podezřelého/špatně nastaveného, tak na to upozorňuje.

- Billing and CostManagement 
  - **Budgets**
  - Anomaly cost detection
 
## Monitoring zdrojů
- AWS resource explorer
  - Pro vyhledávání je vhodné pro jednotlivé instance používat tagy.
