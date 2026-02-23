# README.md — без эмодзи, с мемчиками
markdown
# UnderComms — Undertale/Deltarune Style Chat for Garry's Mod

 ██████╗ ██╗     ██╗████████╗ ██████╗██╗  ██╗██╗      █████╗ ██████╗ 
██╔════╝ ██║     ██║╚══██╔══╝██╔════╝██║  ██║██║     ██╔══██╗██╔══██╗
██║  ███╗██║     ██║   ██║   ██║     ███████║██║     ███████║██████╔╝
██║   ██║██║     ██║   ██║   ██║     ██╔══██║██║     ██╔══██║██╔══██╗
╚██████╔╝███████╗██║   ██║   ╚██████╗██║  ██║███████╗██║  ██║██████╔╝
 ╚═════╝ ╚══════╝╚═╝   ╚═╝    ╚═════╝╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝╚═════╝

**"Reality is just a bug waiting to happen."**

A feature-rich roleplay chat system that makes your GMod server look like a Toby Fox game. 
Pixel-perfect visuals, typewriter effects, proximity chat, and enough customization to make your head spin.

Built because the default chat looks like it was designed in 2004. Oh wait, it was.


## What the hell is this?

UnderComms is a complete replacement for GMod's default chat. It throws out that ugly orange box and replaces it with something that actually looks good.

Think Undertale dialog boxes, but for your server chat. Your players will think you actually give a shit about aesthetics.


## Features (the good stuff)

### 9 Message Styles

Because one chat style is boring as fuck.

|      Command     |   Style   |                      What it does                      |
|------------------|-----------|--------------------------------------------------------|
| `/d`             | Direct    | Normal chat, nothing fancy                             |
| `/r`             | Radio     | Green text with glitches and static. Very tactical.    |
| `/t`             | Telegraph | Chunks of text with morse beeps. STOP                  |
| `/l`             | Letter    | Paper texture, handwritten vibes                       |
| `/w`             | Whisper   | Quiet messages for sneaky bastards                     |
| `/y`             | Yell      | LOUD AS FUCK. ALL CAPS.                                |
| `/me`            | Action    | *does something dramatic*                              |
| `/ooc` or `//`   | OOC       | Out of character, global                               |
| `/looc` or `.//` | LOOC      | Local OOC, for when you need to break character nearby |

### 4 Themes

Pick your poison:

- **Undertale Classic** — Black, white, purple. The OG.
- **Deltarune Cyber** — Neon pink and cyan. Very synthwave.
- **Classic Terminal** — Green on black. Hackerman approved.
- **Crimson Night** — Dark red horror aesthetic. Edgy but cool.

### Proximity Chat

Messages actually have range now. Revolutionary, I know.

- Whisper: ~150 units (basically breathing distance)
- Normal: ~600 units 
- Yell: ~1200 units (half the map hears you)
- Radio/Telegraph/OOC: Global (everyone suffers together)

Dead players and admins hear everything because of course they do.

### Events System

Undertale-style popup notifications. Perfect for:

- Server announcements that players might actually read
- Round starts in TTT
- Whatever dramatic bullshit you want

Screen shake included for extra impact.

### Avatars

- Steam avatars (the normie option)
- 20+ pixel sprites from Undertale/Deltarune (the based option)
- Sans, Papyrus, Frisk, Kris, Spamton... the whole gang

### Sound System

Every letter makes a blip sound. Like Undertale. You're welcome.

- Typewriter effects
- Radio static and glitches
- Morse code for telegraph
- All volumes adjustable because some people hate fun


## Installation

### Workshop (for normal people)

1. Subscribe on Steam Workshop
2. Restart server
3. That's it. Go touch grass.

### Manual (for control freaks)

1. Download from GitHub releases
2. Extract to `garrysmod/addons/undercomms/`
3. Restart server
4. Question your life choices


## Commands

### Chat Styles

/d message     — Direct (or just type normally, nerd)
/r message     — Radio
/t message     — Telegraph  
/l message     — Letter
/w message     — Whisper
/y message     — Yell
/me action     — Action
// message     — OOC (global)
.// message    — LOOC (local)

### Settings

uc_settings           — Opens the settings menu (shocking, I know)
uc_rebuild            — Rebuilds chat UI when it inevitably breaks
uc_theme_set <name>   — Change theme
uc_theme_list         — List themes
uc_sprite_list        — List available sprites
uc_sprite_set <id>    — Set your sprite

### Admin Commands

uc_proximity_toggle   — Toggle proximity (SuperAdmin)
uc_proximity_status   — Show proximity settings
uc_sv_event <title> <text> <type>  — Broadcast event


## Configuration

Edit `lua/glitchlab/sh_config.lua` if you want to customize:

- Chat position and size
- Proximity distances
- Allowed URL domains (whitelist)
- Fade timings
- Debug mode (for when shit breaks)

Most settings are also in the in-game menu because I'm not a monster.


## Compatibility

Tested and working with:

- **DarkRP** — Your /advert and /job commands still work
- **ULX/ULib** — Admin commands pass through
- **TTT** — Dead chat filtering works
- **SAM** — Same deal
- **ServerGuard** — Yep
- **Maestro** — Also yes

If your favorite admin mod breaks, open an issue. I'll probably fix it. Eventually.


## API for Developers

### Trigger Events (Server-side)
lua
GlitchLab.Event("CHAPTER 1", "* The journey begins...", {
    type = "story",
    duration = 5
}, player.GetAll())

### Broadcast Messages (Server-side)
lua
GlitchLab.Chat.Broadcast("Server restarting. Cope.", Color(255, 200, 100))

### Hooks
lua
hook.Add("GlitchLab_PlayerSay", "MyAddon", function(ply, originalText, isTeam, styleName, cleanText)
    -- Do whatever
end)


## Troubleshooting

### Chat not showing up

1. Check console for Lua errors
2. Run `uc_rebuild`
3. Make sure no other chat addon is fighting for dominance
4. Restart map
5. Cry

### No sounds

1. Open settings (`uc_settings`)
2. Make sure "Enable Blip Sounds" is checked
3. Check your volume isn't at 0
4. Check GMod sound settings
5. Accept that silence is golden

### Fonts look like ass

1. The addon tries to use Press Start 2P or VT323
2. If you don't have them, it falls back to Courier New
3. Install better fonts or live with it

### Something else is broken

Open a GitHub issue with:
- What you expected
- What actually happened
- Any console errors
- Your addon list

I'll look at it when I have coffee.


## Roadmap (stuff I might add later)

- GIF support in chat
- Markdown formatting (**bold**, *italic*)
- URL previews
- More themes
- CRT scanline effect
- RPG-style player names (Human [LV 19])

No promises. I have a life. Kind of.


## Credits

**Developed by:** GlitchLab

**Inspired by:** Toby Fox's Undertale and Deltarune. 
If you haven't played them, what are you doing with your life?

**Fonts:** Press Start 2P, VT323 (Google Fonts, SIL Open Font License)

**Special thanks to:**
- The GMod community for being chaotic
- Stack Overflow for existing
- Coffee for keeping me alive


## Legal Shit

**Code:** MIT License — do whatever you want, just don't blame me when it breaks.

**Assets:** Original sprites inspired by Undertale/Deltarune art style. Not official, not affiliated with Toby Fox.

**Disclaimer:** This is a fan project. All trademarks belong to their respective owners. Don't sue me, I'm poor.


## Support

If you like this addon:

- Star it on GitHub
- Rate it on Workshop
- Tell your friends
- Send me pizza money

If you hate it:

- Open an issue
- Be constructive
- Don't be a dick


* You are filled with DETERMINATION.

* Or caffeine. Probably caffeine.


**GlitchLab | UnderComms v1.0.0**

"It just works." — Todd Howard (lying)
