# bebok-plugins

Central plugin registry for [Bebok](https://github.com/henrykbrzoska/bebok).

`plugins.json` is the source of truth for available plugins. Bebok fetches
it (raw) to build the plugin list in Settings → General, installs a plugin
by cloning its `url` at the **latest tag**, and validates the plugin's own
`bebok-plugin.json` manifest after cloning.

## Adding a plugin

1. Publish the plugin repo (public) with a `bebok-plugin.json` manifest in
   its root:
   ```json
   {
     "name": "my-plugin",
     "version": "1.0.0",
     "min_engine_version": "1.5.0",
     "description": "What the plugin does."
   }
   ```
2. Tag a release (`git tag v1.0.0 && git push origin v1.0.0`) — Bebok
   installs the latest tag, never a floating branch.
3. Add an entry to `plugins.json` and open a PR here.

Only public repos are supported for now.
