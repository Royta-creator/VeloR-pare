# ZELDA DARK HUD — Guide d'installation Roblox Studio
## Structure des fichiers

```
ZeldaHUD/
├── StarterGui/
│   └── HUD/
│       └── LocalScript.lua       ← Interface + logique client
└── ServerScriptService/
    └── HUDServer.lua             ← Gestion serveur + API
```

---

## Installation pas à pas

### 1. ScreenGui (interface)
1. Dans **StarterGui**, crée un **ScreenGui** nommé `HUD`
2. Coche **ResetOnSpawn = false**
3. Dans ce ScreenGui, crée un **LocalScript**
4. Colle le contenu de `StarterGui/HUD/LocalScript.lua`

### 2. Script serveur
1. Dans **ServerScriptService**, crée un **ModuleScript** nommé `HUDServer`
2. Colle le contenu de `ServerScriptService/HUDServer.lua`

### 3. RemoteEvents (auto-créés)
Les deux scripts créent automatiquement dans `ReplicatedStorage` :
```
ReplicatedStorage/
└── HUDEvents/
    ├── TakeDamage    (RemoteEvent)
    ├── Heal          (RemoteEvent)
    ├── UseAbility    (RemoteEvent)
    ├── QuestUpdate   (RemoteEvent)
    └── ShowNotif     (RemoteEvent)
```
Tu n'as rien à créer à la main.

### 4. ValuesFolder (optionnel mais recommandé)
Les stats sont auto-créées au join du joueur. Structure :
```
Player/
└── Stats/                (Folder)
    ├── HP                (NumberValue)  défaut: 7.5
    ├── MaxHP             (NumberValue)  défaut: 10
    ├── Stamina           (NumberValue)  défaut: 75
    ├── Rubis             (NumberValue)  défaut: 0
    └── Quests/           (Folder)
        ├── Quest1        (StringValue)  "texte|sous-titre|progression|statut"
        ├── Quest2        (StringValue)
        └── Quest3        (StringValue)
```

---

## Utilisation de l'API serveur

Dans n'importe quel Script serveur :

```lua
local HUDServer = require(game.ServerScriptService.HUDServer)

-- Infliger des dégâts (1.5 = 1.5 cœurs)
HUDServer.damage(player, 1.5)

-- Soigner
HUDServer.heal(player, 3)

-- Ajouter des rubis
HUDServer.addRubis(player, 50)

-- Mettre à jour une quête (index, progression 0-100, "active"/"done")
HUDServer.updateQuest(player, 1, 80, "active")
HUDServer.updateQuest(player, 2, 100, "done")

-- Notification personnalisée
HUDServer.notify(player, "Boss vaincu !", "Le Gardien ne te menace plus")
HUDServer.notifyAll("Événement mondial", "Un portail s'ouvre...")
```

---

## Keybinds (compétences)
| Touche | Compétence      | Coût stamina |
|--------|----------------|--------------|
| Q      | Bombe Ancienne | 15           |
| E      | Magnésis       | 20           |
| R      | Stasis         | 10           |
| F      | Cryonis        | 18           |

Modifiables dans `CFG.ABILITY_KEYS` et `CFG.ABILITY_COSTS` du LocalScript.

---

## Personnalisation rapide

Tout est dans le bloc `CFG` en tête de chaque fichier :
- **Couleurs** : modifie `CFG.GOLD`, `CFG.CHARCOAL`, etc.
- **HP maximum** : `CFG.MAX_HP`
- **Cooldowns** : `CFG.ABILITY_COOLDOWNS = {8, 12, 15, 10}`
- **Vitesse regen stamina** : `CFG.STAMINA_REGEN_RATE` (points/seconde)
- **Quêtes initiales** : `CFG.DEFAULT_QUESTS` dans HUDServer.lua
