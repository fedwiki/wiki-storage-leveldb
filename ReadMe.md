# Wiki Storage LevelDB

An experimental module to provide LevelDB storage for an external module for
Federated Wiki, rather than being built into the core.

The motivation for this is that not everybody is using LevelDB for storage, and
as part of the core it requires rebuilding whenever the server module is
updated/redeployed.

## Using LevelDB for Wiki Storage

The following steps will need to be followed:

1. Take a copy of the [fedwiki/wiki-node](https://github.com/fedwiki/wiki-node)
repository. *Either create a fork on the GitHub site, or clone a copy either
locally or to where you wish to install Federated Wiki.*

2. In your copy, edit `package.json` to add the following line to the dependencies:

```
    "wiki-storage-leveldb": "*",
```

3. If you are using git for deployment, commit this change to git.

4. Install your modified version of Federated Wiki, either:

  * running `npm install 'your-github-id'/wiki-node`, if you are using github
  for deployment, or

  * if you modified `package.json` inplace, by running `npm install` from within
  the modified directory. See [npm-install](https://www.npmjs.org/doc/cli/npm-install.html)
  for more ideas.

5. When starting Federated Wiki you will need to tell it to use LevelDB. This
is done by adding the following configuration setting:

```
--database '{"type": "wiki-storage-leveldb"}'
```

## Developer Notes

Should there be a need to modify this package, there is a test file
`test/leveldb.coffee` that can be copied to the `test` directory of the
wiki-node-server repository that you are developing with.

**N.B.** the plugin page
testing also requires a copy of the `wiki-plugin-chart` repository to be alongside
the wiki-node-server repository.
