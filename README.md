### 🏆 Why Do Achievements Turn Off in Some Addons? (And How to Fix It!)

If you've ever installed an addon in Minecraft Bedrock and suddenly noticed achievements are disabled, you're not alone. Here's why it happens and how to make any addon achievement-friendly.

### 🔍 Why Achievements Turn Off

Minecraft disables achievements when it detects something that could give an unfair advantage or modify the game in a way that isn't "vanilla." The most common triggers are:

- Missing the "addon flag" in the pack's manifest – without "product_type": "addon", Minecraft assumes the pack might be a cheat world.
- Experimental features are enabled (like Holiday Creator Features, Beta APIs, etc.).
- Cheats are turned on in the world settings (either manually or via command blocks).
- The world was created as a template with locked game rules.

### 🛠️ How to Make an Addon Achievement-Friendly

1️⃣ Add the Magic Line to Both Manifests

Open the addon's behavior_pack/manifest.json and resource_pack/manifest.json files. Locate the "metadata" section – if it doesn't exist, add it at the same level as "header" and "modules". Inside, include:

```json
"metadata": {
  "product_type": "addon"
}
```

Example placement:

```json
{
  "format_version": 2,
  "header": { ... },
  "modules": [ ... ],
  "dependencies": [ ... ],
  "metadata": {
    "product_type": "addon"
  }
}
```

Make sure the "format_version" is 2 or higher.

2️⃣ Turn Off Experimental Features

In the world settings where you apply the addon, go to Experiments and disable any toggles like "Holiday Creator Features" or "Beta APIs" unless the addon absolutely requires them. If it does, the addon may never be achievement-compatible.

3️⃣ Never Enable Cheats

Keep your world set to Survival with Allow Cheats: OFF. Even if you're the host, cheats should remain off for achievements to stay active. (You can still use commands if you're op, but don't flip the cheat switch.)

✅ Quick Checklist

- Both behavior and resource packs have "product_type": "addon" in their manifests.
- "format_version" is 2 or higher.
- Experimental features are disabled in world settings.
- Cheats are not enabled in the world.
- Test by loading the world and checking if the achievement icon is still unlocked.

🎉 You're Ready!

Now you can enjoy custom addons without losing your achievements. Share this guide with others who might be struggling – together we can keep our worlds fun and rewarding.


Main contributor: @BluePhinix

Revised by: @TheVenlark
