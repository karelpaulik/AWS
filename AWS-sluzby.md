## AWS služby
- EC2
  - Load balancer
- Lightsail
- S3  (zde se dá nastavit: S3 Storage Lens - aby sledoval velikosti existujicích bucketů)
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
