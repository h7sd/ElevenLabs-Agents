# ElevenLabs Agents for Scam With Your Friends

Installs ElevenLabs Agents, its AI Backend dependency and the shared library. The optional setup step installs the local bridge. Node.js 22.13 or newer and your own ElevenLabs configuration are required.

Download **ElevenLabs-Agents-1.0.1.zip** from [Releases](https://github.com/h7sd/ElevenLabs-Agents/releases/latest). Its ZIP contains only root-level DLLs and one optional post-install script. The shared library is installed to BepInEx/core; plugin DLLs go to BepInEx/plugins.

The stock launcher offers setup steps only for catalogue entries. For a direct-URL installation, extract the ZIP and run its root script yourself with `-GameDir "C:\Path\To\Game"` while the game is closed.

[Source and build scripts](https://github.com/h7sd/scam-with-your-friends-mods/tree/edacd91f088f9601b278bdd4cff7e172e09c1ae3/mod), [package instructions](https://github.com/h7sd/scam-with-your-friends-mods/blob/edacd91f088f9601b278bdd4cff7e172e09c1ae3/catalogue/README.md). Source revision: `edacd91f088f9601b278bdd4cff7e172e09c1ae3`. Licence notices are included in the post-install script.

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
    },
    {
      "fileName": "ScamWYF.AiBackend.dll",
      "folder": "plugins",
      "expectsPluginAttribute": true
    },
    {
      "fileName": "ScamWYF.Modding.Core.dll",
      "folder": "core",
      "expectsPluginAttribute": false
    }
  ],
  "postInstall": [
    {
      "script": "setup-elevenlabs-agents.ps1",
      "description": "Downloads and installs the local ElevenLabs bridge and opens its setup page. Requires Node.js 22.13 or newer. Skipping leaves speech and AI unavailable until you set up and start the bridge yourself."
    }
  ]
}
```

Unofficial community mod, unaffiliated with the game developer or the external service.
