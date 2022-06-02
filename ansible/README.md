## Section 23 : ansible Vault
<details>

- using ansible vault for encrypt :
```
ansible-vault encrypt aws.yaml
```

- using ansible vault for decrypt cmd not file (ask pwd) :
```
ansible-vault view aws.yaml
```

- using ansible vault for decrypt and run file cmd (ask pwd) :
```
ansible-playbook -i aws-yaml --ask-vault-pass playbook.yaml
```

- for rekey password in file encrypted :
```
ansible-vault rekey aws.yaml
```

- using ansible vault for decrypt cmd file none encrypt (ask pwd) :
```
ansible-vault decrypt aws.yaml
```
</details>

## Section 24: using ansible with hashicorp vault
<details>

### Description:
Will need HashiCorp Vault <br/>
You may run into issues - ask the FB Group and Check Google <br/>
Mac users: You will need to uninstall of ansible and use pip to reinstall <br />
Will need the havc python module: pip install havc <br />

### Resources
Link to install Vault: https://learn.hashicorp.com/tutorials/vault/getting-started-install <br />
Link to the documentation for the vault module: https://docs.ansible.com/ansible/latest/plugins/lookup/hashi_vault.html <br />
If you run into: in progress in another thread when fork() was called <br />
Run: export OBJC_DISABLE_INITIALIZE_FORK_SAFETY=YES <br />
Then re-run the command <br />
https://www.vaultproject.io/


</details>