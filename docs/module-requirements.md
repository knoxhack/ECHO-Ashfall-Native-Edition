# Ashfall Native Edition Module Requirements

The pack manifest declares module requirements instead of hard-coding every module file by hand.

```json
{
  "moduleArtifactFamily": "echo-addon",
  "moduleRequirements": [
    {
      "id": "echoashfallprotocol",
      "version": "1.0.0",
      "required": true
    }
  ]
}
```

The launcher resolves the default artifact name as `<module>-<version>.echo-addon`. Individual requirements can override `assetName`, `path`, `sha256`, `size`, `side`, or `artifactFamily`.
