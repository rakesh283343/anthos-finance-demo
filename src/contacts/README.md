# Contacts Service

The contacts service stores a list of saved accounts associated with a user.
Data from the contacts service is used for drop down in "Send Payment" and "Deposit" forms.

Implemented in Python with Flask.

### Endpoints

| Endpoint                | Type  | Auth? | Description                                                        |
| ----------------------- | ----- | ----- | ------------------------------------------------------------------ |
| `/contacts/<username>`  | GET   | 🔒    |  Retrieve a list of saved accounts for the authenticated user.     |
| `/contacts/<username>`  | POST  | 🔒    |  Add a new saved account for the authenticated user.               |
| `/ready`                | GET   |       |  Readiness probe endpoint.                                         |
| `/version`              | GET   |       |  Returns the contents of `$VERSION`                                |


### Environment Variables

- `VERSION`
  - a version string for the service
- `PORT`
  - the port for the webserver
- `ACCOUNTS_DB_ADDR`
  - the address and port of the `accounts-db` service
- `LOCAL_ROUTING_NUM`
  - the routing number for our bank
- `PUB_KEY_PATH`
  - the path to the JWT signer's public key, mounted as a secret

### Kubernetes Resources

- [deployments/contacts](/kubernetes-manifests/contacts.yaml)
- [service/contacts](/kubernetes-manifests/contacts.yaml)
