# ElevenLabs Agents for Scam With Your Friends

Setup installs the required shared Core, AI Backend 1.1.0 and the local ElevenLabs bridge. Node.js 22.13 or newer and your own ElevenLabs configuration are required. Skipping setup requires these dependencies and a running bridge to be installed manually.

Download **ElevenLabs-Agents-1.0.2.zip** from [Releases](https://github.com/h7sd/ElevenLabs-Agents/releases/latest). The ZIP has exactly two root files:

- `ScamWYF.ElevenLabsAgents.dll`
- `setup-elevenlabs-agents.ps1`

Package 1.0.2 changes distribution only; the DLL version remains 1.0.1. There is no launcher, dependency DLL or runtime inside this mod ZIP. Required dependencies are downloaded separately by setup using fixed HTTPS URLs and SHA-256 checks. Licence notices are included in the script.

The stock launcher offers setup only for catalogue installations. If using a direct ZIP URL, extract it and run `setup-elevenlabs-agents.ps1 -GameDir "C:\Path\To\Game"` with the game closed.

[Source](https://github.com/h7sd/scam-with-your-friends-mods/tree/b1732624d24d933de3af0a4a09ef74af90a9f461/mod) · [Package and dependency instructions](https://github.com/h7sd/scam-with-your-friends-mods/blob/b1732624d24d933de3af0a4a09ef74af90a9f461/catalogue/README.md)

Catalogue entry:

```json
{
  "owner": "h7sd",
  "repo": "ElevenLabs-Agents",
  "displayName": "ElevenLabs Agents",
  "summary": "Uses a local ElevenLabs Agents bridge for caller speech, microphone recognition and AI responses, with character-specific voices and language controls.",
  "files": [
    {
      "fileName": "ScamWYF.ElevenLabsAgents.dll",
      "folder": "plugins",
      "expectsPluginAttribute": true
    }
  ],
  "postInstall": [
    {
      "script": "setup-elevenlabs-agents.ps1",
      "description": "Downloads the required Core, AI Backend and local ElevenLabs bridge, then opens setup. Requires Node.js 22.13+. If skipped, these dependencies and a running bridge must already be installed for the mod to work."
    }
  ]
}
```
