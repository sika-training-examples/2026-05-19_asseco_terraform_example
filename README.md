> [!TIP]
> <a href="https://ondrej-sika.cz/skoleni/terraform"><img src="https://img.shields.io/badge/Školení%20Terraform-by%20Ondřej%20Šika-7B42BC?style=for-the-badge&logo=terraform&logoColor=white" style="width: 100%; height: auto;" alt="Školení Terraform by Ondřej Šika" /></a>
>
> 🚀 Naučte se, jak efektivně pracovat s **Terraformem**! Praktické školení vedené [Ondřejem Šikou](https://ondrej-sika.cz).
>
> 👉 [Více informací a registrace zde](https://ondrej-sika.cz/skoleni/terraform)

# example

## Connect postgres from VM

```
TOKEN=$(curl -s 'http://169.254.169.254/metadata/identity/oauth2/token?api-version=2018-02-01&resource=https%3A%2F%2Fossrdbms-aad.database.windows.net' -H 'Metadata: true' | jq -r .access_token)
POSTGRES_HOST=ondrejsika1-pg.postgres.database.azure.com
psql "host=$POSTGRES_HOST port=5432 dbname=postgres user=vm-ondrejsika1 password=$TOKEN sslmode=require"
```