# bower-snap

Simple wrapper of bower-locker that creates a snapshot for future comparison(instead of locking the dependencies. The snapshot will be useful to compute the delta in (transitive) dependencies, which can be useful for denugging/explaining differences


## Installation
Please install via:
```
npm install bower-snap --save
```
In order to run bower-snap, git needs to be installed.
Also, for now, make sure you run node >= 8, you might want to use nvm[https://github.com/creationix/nvm/blob/master/README.md] for this.


## Creating a snapshot
Create a .bower-snap.json file
```
bower-snap --snap
```

## Comparing
To see the difference between your current bower_components folder and the current .bower-snap.json file:
```
bower-snap --compare
```
To see the difference between your current bower_components folder and a bower-snap from the past: provde a tagname or commit hash
```
bower-snap --compare <commit-hash>
```
Provide the full path to a bower-snap json you have locally on you machine. (This can be handy for seeing the difference between two (unrelated) repos)
```
bower-snap --compare-path '/my/snapshot/path.json'
```


## Committing snapshots
Bower-snapshots can be comitted. They are then tied to the commit(or tag) If you created a new .bower-snap file, makes sure it reflects the correct status on your commit
