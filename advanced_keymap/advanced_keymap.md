# Advanced Keymap

> A feature-rich keymap for the Silakka54 with homerow mods, full symbol layer, Bluetooth controls, and numpad. Designed for power users who want to get the most out of 54 keys.

---

## What's different from the default keymap

The default keymap is intentionally minimal and easy to understand. This advanced version adds several ZMK power features that take more time to learn but significantly increase efficiency.

---

## Homerow Mods

The biggest change. The home row keys double as modifiers when held:

```
Left hand:   A = GUI    S = ALT    D = CTRL    F = SHIFT
Right hand:  J = SHIFT  K = CTRL   L = ALT     ; = GUI
```

This means your modifiers are always one step away from your resting position — no more reaching for Ctrl or Shift in the corners.

**How it works:** tap quickly for the letter, hold slightly longer for the modifier. The keyboard uses a `balanced` hold-tap flavor with the following tuning:

| Parameter | Value | Effect |
|-----------|-------|--------|
| `tapping-term-ms` | `280` | Time to decide tap vs hold |
| `quick-tap-ms` | `175` | Fast re-tap always sends key, not modifier |
| `require-prior-idle-ms` | `150` | Prevents misfires during fast typing |

> **Adjustment tip:** If modifiers trigger accidentally while typing fast, increase `require-prior-idle-ms` to `200`. If they're hard to activate, lower `tapping-term-ms` to `220`.

---

## Layers

### Base — QWERTY + homerow mods

Standard QWERTY layout with homerow mods on the home row. `TAB` replaces `CTRL` on the outer edge since CTRL is now on the homerow. Left lower thumb key activates **Lower**, left upper activates **Raise**.

### Lower — Symbols + Bluetooth + Media

| Row | Left side | Right side |
|-----|-----------|------------|
| Top | BT profile 1–5, BT clear | USB / BLE output switch, BT clear all |
| Middle | `! @ # $ %` | `^ & * ( ) ~` |
| Home | `` ` - = [ ] `` | `\| _ + { } "` |
| Bottom | Prev / Next / Play / Vol dn / Vol up | Mute, F1–F5 |
| Thumb | — | F6 F7 F8 |

### Raise — Numpad + Navigation + F-keys

| Row | Left side | Right side |
|-----|-----------|------------|
| Top | F1–F5 | F6–F11 |
| Middle | — / Home / End | ÷ 7 8 9 − |
| Home | — / PgUp / PgDn | × 4 5 6 + |
| Bottom | — / ← / → | 0 1 2 3 ↑ Enter |
| Thumb | ↓ | — . |

### Adjust — System controls

Activates automatically when **Lower + Raise are held simultaneously** (no extra key needed).

| Key | Action |
|-----|--------|
| Top-left | `sys_reset` — soft reset |
| Top-right | `sys_reset` |
| 2nd-left | `bootloader` — enter DFU mode for flashing |
| 2nd-right | `bootloader` |

---

## Combos

All combos work on the Base layer. Press both keys within 50ms.

| Keys | Output | Notes |
|------|--------|-------|
| `R` + `T` | `=` | |
| `E` + `R` | `+` | |
| `S` + `D` | `[` | |
| `A` + `S` | `{` | |
| `F` + `G` | `]` | |
| `J` + `K` | `}` | |
| `U` + `I` | `(` | New |
| `I` + `O` | `)` | New |
| `O` + `P` | `Backspace` | New |
| `P` + `-` | `Delete` | New |
| `Q` + `W` | `Escape` | Useful with homerow mods |

---

## Tap-Dance Keys

| Key | Single tap | Double tap |
|-----|-----------|------------|
| Bottom-left (was Shift) | `Shift` | `Caps Lock` |

---

## Learning Curve

Homerow mods are the hardest part to get used to. Expect **1–2 weeks** before they feel natural. During that time you may experience:

- Accidental modifier triggers → increase `require-prior-idle-ms`
- Modifiers not activating → decrease `tapping-term-ms`
- Conflicts with fast same-hand shortcuts → the `hold-trigger-key-positions` in the behavior definition restricts each hand's mods to only trigger when the *opposite* hand presses a key, which prevents most conflicts

---

## How to use this keymap

1. Download `lily58.keymap` from this repository
2. Replace `config/lily58.keymap` with it
3. Push to GitHub — the Actions workflow will build new firmware automatically
4. Flash as usual

You can further customize it using [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/) — all behaviors, combos, and layers are fully compatible with the visual editor.
