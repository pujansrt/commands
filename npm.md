# NPM Commands

```bash
tsc         # typescript
n           # Version manager for node
ng          # Angular
npkill      # Search subdirectory for deletes selected node_modules directory 
tldr        # tldr;
```

Create a tarball from a package

```
npm pack
```

Checks for outdates packages
```
npm outdated
```

Remove extraneous packages
Removes packages that are not listed on the parent package's dependencies list.

```
npm prune
```


Reduce duplication
Dedupe searches the local package tree and tries to simplify its structure by moving dependencies further up the tree. This way, they can be shared more effectively by multiple dependent packages.
```
npm dedupe
```

