# Wiki Storage LevelDB

An experimental module to provide LevelDB storage for an external module for
Federated Wiki, rather than being built into the core.

The motivation for this is that not everybody is using LevelDB for storage, and
as part of the core it requires rebuilding whenever the server module is
updated/redeployed.
