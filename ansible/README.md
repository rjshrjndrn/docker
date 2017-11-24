### Important notes

Container will share your ssh-agent for better ssh compatibility

` -v $SSH_AUTH_SOCK:/ssh-agent:ro `

#### pre-requisites
your user must be in docker group, or you'll be having ssh compatibility errors.

` sudo usermod -aG docker $(whoami) `

after this you'll have to logout and login to your account

### Example 

If you're using ansible 1.9.5

```
cd 1.9.5

chmod +x ansible1.9.5

mv ansible1.9.5 /usr/local/bin

ansible1.9.5 ansible-playbook -i hosts play.yml
```
