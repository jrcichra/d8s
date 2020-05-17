# d8s
Create and manage developer pods in Kubernetes - (w/ early support to retain homedirs in PVs)

## Usage
```
   ./d8s

   help                  this screen
   install [devbox]      install this devbox into kubernetes    
   uninstall [devbox]    uninstall this devbox from kubernetes    
   list 		 list all the installed devboxes
```

Run `./d8s install devbox` for a quick deployment. See it with `./d8s list`

## Configuration
+ See the `devbox` file - customize/copy the Dockerfile in `Dockerfiles/Dockerfile`, build your own: `docker build -t <your-tag-here> .` and reference it in a new config file. Then run `./d8s install <filename>`
+ Make sure to keep the SSH configuration section (NOTE: The password is baked into the Dockerfile (root:root), looking to change in future versions [ or just wrap kubectl exec, but having sshd is nice ])
+ Anything done in your home directory (specified mount in the config file) should be saved as a PV by whatever the default provisioner for your cluster is
