# Blueprints to deploy app for your team

## Install kpt
```
https://googlecontainertools.github.io/kpt/installation/
```

## Fetch the blueprints package
```
kpt pkg get git@github.com:phanimarupaka/blueprints.git@v0.1.0 ./blueprints_alice
cd blueprints_alice
git init .
git add .
git commit -am "Initial commit"
```

## Set the values for blueprints
```
kpt cfg list-setters namespaces
kpt cfg set namespaces namespace_setter hellospace
kpt cfg list-setters app
kpt cfg set app namespace_setter hellospace
kpt cfg set app teamname_setter team1
```

## Preview and Apply the resources to cluster
```
kpt live init namespaces
kpt live init app
kpt live preview namespaces
kpt live apply namespaces
kpt live preview app
kpt live apply app
```

## Destroy
```
kpt live destroy app
kpt live destroy namespaces
```