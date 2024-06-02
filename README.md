## :computer: Light terminal setup for Debian 12  
the setup file has the following packages:

- zsh (oh my zsh, PowerLevel10K, zsh autosuggestions)
- fzf & file preview
- batcat (colored cat)
- tmux
- LSD (better ls)
- neovim

#### Setup Steps 

- Install ansible

```bash 
sudo apt-get install ansible
```
- Create a file named inventory.ini: 

```bash
echo -e "[local]\nlocalhost ansible_connection=local" > inventory.ini
```
- Run the playbook with Ansible:
  - Update the following variables in `setup.yaml`:
    - `ansible_user`
    - `ansible_user_dir`
    - `neovim_version`

```bash
ansible-playbook -i inventory.ini setup.yaml --ask-become-pass
```
