### You'll need direnv and git, or you're going to have a bad time.
this repo assumes you have direnv as well as git configured and running properly. Run `direnv allow`in this repository to make your life easier. Else you will have to `source .envrc` for the rest of the scripts to work


### edit .awsrc with your creds and region
### edit configs/settings.rc 
and provide your QUAKE_TLD and your QUAKE_CLUSTER_NAME. This will be used to create certs, a hosted zone and a few other things. you can take care of delegating DNS with your provider after you are past the bootstrap (terraform) step.

### run 
```direnv allow```

### shoot 
```installers/quake --install``` 
to install all required clis into the bin dir of this repo. 

### pick up health
```installers/quake --bootstrap```
To run terraform and manipulate the outputs into config files

### finish level
```installers/quake --deploy```
to interpolate the provided kops cluster template with defaults and terraform outputs. It will safe a full cluster and a clusters vars YAML into the state directory.


### you should now have a kubernetes cluster up and running 
