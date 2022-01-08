# Argocd-account
A Helm chart for argocd-account with rbac settings.

## Manage users
The Argo CD CLI provides set of commands to set user password and generate tokens.

### Get full users list
```sh
$ argocd account list
```

### Get specific user details
```sh
$ argocd account get --account <username>
```

### Set user password
```sh
# if you are managing users as the admin user, <current-user-password> should be the current admin password.
$ argocd account update-password \
  --account <name> \
  --current-password <current-user-password> \
  --new-password <new-user-password>
```

### Generate auth token
```sh
# if flag --account is omitted then Argo CD generates token for current user
$ argocd account generate-token --account <username>
```