# chart to install nbpcloud-billing api services


## Install helm chart
```
 helm install cloudbilling --namespace cloudbilling . --set useHelm3=true --debug 
```

## Uninstall helm chart
```
 helm uninstall cloudbilling --namespace cloudbilling . 
 
```


## Secrets symbolic links
secrets are not included in the directoy that is put on the repo instead it is inthe ~/.config directory. The templates are as shown below
```
ln -s /home/vagrant/.config/dockersecret .dockersecret 
ln -s /home/vagrant/.config/dbstring .dbstring
```
### dockersecret template
```
{
    "auths":
    {
        "registry.gitlab.com":
        {
            "username":"email",
            "password":"password/personne; token"
           
        }
    }

}
```

### dbstring template
```
mongodb://user:password@db-instllation-name.svc.cluster.local:27017/dbname
```

### Testing the service from local machine
```
 kubectl port-forward -n namespace svc/svc-name 4000:80
 ```