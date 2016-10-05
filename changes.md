# ** THE CHANGES HASN'T been tested ( sort of ) **

NB: i just been able to test using my local change after i ``` peru sync ``` from the main repo, so this fork hasn't been tested but to use it on snowplow vagrant file, should be kinda like this :

( oh, and i also test it with ubuntu xenial cloud image wich you can find [in here](https://cloud-images.ubuntu.com/xenial/current/) , not ubuntu/trusty64 )

# Up.Bash
From:

```
su - -c "source ${env_setup} && ${vagrant_dir}/ansible/bin/ansible-playbook ${vagrant_dir}/${pb} --connection=local --inventory-file=${hosts}" vagrant
```

TO
```
su - -c "source ${env_setup} && ${vagrant_dir}/ansible/bin/ansible-playbook ${vagrant_dir}/${pb} --extra-vars=\"hosts=$HOSTNAME remote_user=$USER\" --connection=local --inventory-file=${hosts}" $USER

```


# peru.yaml
From:
```
git module ansible_playbooks:
    url: https://github.com/snowplow/ansible-playbooks.git

```

To
```
git module ansible_playbooks:
    url: https://github.com/chocopowwwa/ansible-playbooks.git
```
