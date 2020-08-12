# certbot Container

## _setting file format_

```
###certbot###
domain:example.com
domain:example.org,example.net
```

## _up container_

```
./script.sh
sudo firewall-cmd --add-forward-port=port=80:proto=tcp:toport=1080 --permanent
sudo firewall-cmd --reload
podman play kube podman.yml
```

#### _SE-Linux setting_

```
sudo mkdir -p -m 777 /home/podman/certbot_pod/letsencrypt /home/podman/certbot_pod/log
sudo semanage fcontext -a -t container_file_t /home/podman/certbot_pod
sudo restorecon -R /home/podman
```

