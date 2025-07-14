
Requirements:

- APP Registration in Azure
- Azure Key Vault
- Access (User or Service Principal) to the Key Vault to retrieve the Secrets
- Important: I use Parameter in the Scripts.


1. Get Secrets from Azure Key Vault

This script securely retrieves sensitive credentials (such as client_id, client_secret, and tenant_id) from an Azure Key Vault instance. It uses the mssparkutils.credentials.getSecret method to fetch secrets by their names, ensuring that sensitive information is not hardcoded in the source code. These credentials are typically used for authenticating with Azure services.

Key Steps:

Connects to Azure Key Vault using the specified vault name.
Retrieves secrets for application client ID, client secret, and tenant ID.
Stores the retrieved values in variables for use in authentication or API calls.




2. Create Bearer Token

This script authenticates with Microsoft Azure Active Directory using the OAuth2 client credentials flow. It sends a POST request to Azure’s token endpoint with the required credentials (client_id, client_secret, and tenant_id) and retrieves a bearer token. The token can then be used to authenticate subsequent API requests to Azure services.

Key Steps:

Constructs the token request URL using the tenant ID.
Sends client credentials to obtain an access token.
Extracts and stores the token_type and access_token from the response.