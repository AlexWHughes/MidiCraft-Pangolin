# MidiCraft-Pangolin
# MIDI Device LED & Button Mapping

## Overview
This repository documents the **MIDI implementation** for my device, including **LED control, button remapping, and color mapping**. The purpose is to provide a structured reference for custom MIDI feedback and lighting behavior.

## Important Changes
🔹 **Button Remapping**: I have **remapped all buttons** to start at **Channel 1, Note 1 (0x01)** rather than **Note 0 (0x00)**.

🔹 **Color Mapping Discovery**: The velocity values that control LED colors have been mapped, and they correspond to specific color outputs.

---

## 🎛 MIDI Button Mapping
### **Remapped Button Assignments**
| Button # | MIDI Note | Hex Value |
|----------|----------|-----------|
| 1        | 1        | 0x01      |
| 2        | 2        | 0x02      |
| 3        | 3        | 0x03      |
| ...      | ...      | ...       |
| 20       | 20       | 0x14      |

🔹 **All buttons now start from Note 1 (`0x01`) instead of Note 0 (`0x00`).**

---

## 🎨 LED Color Mapping
The LED colors are controlled via **Note On messages** with specific **velocity values**.

| **Velocity (Hex)** | **Color Output** |
|--------------------|-----------------|
| `0x11` (17)       | White           |
| `0x12` (18)       | Red             |
| `0x13` (19)       | Yellow          |
| `0x14` (20)       | Orange          |
| `0x15` (21)       | Yellow          |
| `0x16` (22)       | Sea Green?      |
| `0x17` (23)       | Green           |
| `0x18` (24)       | Cyan            |
| `0x19` (25)       | Blue            |
| `0x1A` (26)       | Blue (again?)   |
| `0x1B` (27)       | Violet          |
| `0x1C` (28)       | Pink            |
| `0x1D` (29)       | Warm White      |
| `0x1E` (30)       | Cold White      |
| `0x1F` (31)       | Off             |
| `0x20` (32)       | Dark Blue       |
| `0x21` (33)       | Dark Green      |
| `0x22` (34)       | Dark Cyan       |
| `0x23` (35)       | Dark Purple     |

---

## 🎛 MIDI Command Reference
### **Turn Button LEDs On (Example for Green)**
```plaintext
MidiOut 0x90, 0x14, 0x17  # Note 20 (0x14) - Green
```

### **Turn Off All LEDs**
```plaintext
MidiOut 0x80, 0x01, 0x00  # Note Off - Note 1
MidiOut 0x80, 0x02, 0x00  # Note Off - Note 2
...
MidiOut 0x80, 0x14, 0x00  # Note Off - Note 20
```

---

## 🚀 Next Steps
✅ Further refine color mappings and confirm additional LED behaviors.
✅ Document flashing/blinking behavior if applicable.
✅ Explore possible additional functions via Control Change (CC) messages.

If you'd like to contribute to this documentation, feel free to open an issue or submit a PR! 🎛✨


