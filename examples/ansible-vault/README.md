ansible-vault
=============

Ansible-vault is a powerful tool to store and manage secrets that you want to keep
with your repository but don't want to store as plain text.

edit-secrets
------------

Edit (or view) contents of ./vars/secrets.yml using vim

```bash
make edit-secrets
```

The supplied secrets contains the vault password for sub-vaulted files located
within `./repos/foo/vars/secrets.yml` and `./repos/bar/vars/secrets.yml`.

generate-vault-password
-----------------------

*Vault password files shouldn't be stored within a repository as plain text - it
should be managed separately.*

To be able to run this example you will need vault passwords.

```bash
make generate-vault-password
```

This playbook will

- create `./.secrets` directory
- create `./.secrets/ansible-learning.vault` with password used to decrypt
  `./vars/secrets.yml`


single-vault
------------

Assume you are running a playbook that needs to read some sensitive information stored
in `./vars/secrets.yml`.

```bash
make single-vault
``` 

Show that secrets can be vaulted and displayed with correct vault-password file

multiple-vaults
---------------

Manage a vault of vaults to centrally manage vault passwords for other repositories.

Suppose you have a number of separate repositories that have different vault passwords.
You may want to do this for a number of reasons: 

- Limit blast radius if a vault password is compromised
- Different teams manage different repositires
- Ensure repositories are self-contained

However, with multiple repositories using different vault files, you will need some way
to manage these vault passwords.

*Structure*

We're going to use this repository's secrets `./vars/secrets.yml` to manage the vault
passwords for repository `repo/foo` and `repo/bar`. Each have their own secrets, vaulted
with different keys `./secrtes/foo.vault` and `./secrets/bar.vault`.


```bash
make multiple-vaults
```

Using the primary vault password/secrets, generate vault passwords for repositories
`foo` and `bar`. Once vault passwords generated, verify by running playbooks in
sub-repositories.

Show secrets for separate repositories.


questions
---------

*Where do secrets belong?*

Secrets and vault files shouldn't be stored as plain text within a repositories. Instead
they should be stored either within the profile directory (~/.secrets) or stored via a
key management service (e.g. AWS KMS).
