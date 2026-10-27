# Anycubic Kobra Plus mit Klipper

Klipper-Konfiguration (Raspberry Pi 4, MainsailOS) und PrusaSlicer-Profile für eine Anycubic Kobra Plus (TriGorilla Pro A, HC32F460).

- `klipper_config/`: Inhalt von `~/printer_data/config/`
- `prusaslicer/`: Profile aus `%APPDATA%\PrusaSlicer`

## Wichtige Werte (abweichend von der Klipper-Vorlage)
| Einstellung | Wert | Grund |
|---|---|---|
| stepper_z run_current / sense_resistor | 1.3 A / 0.110 | Anycubic Z_CURRENT 1300, ein Treiber für beide Z-Motoren |
| Z-Treibermodus | StealthChop | SpreadCycle bewegt Z nicht |
| extruder rotation_distance | 7.901 | Anycubic 405 Schritte/mm |
| probe speed / lift_speed | 2.5 / 5 | 1 mm/s driftete, 5 mm/s drückte zu hart |
| stepper_z homing_speed / second_homing_speed | 2.5 / 2.5 | s. o. |
| probe z_offset | -0.10 | Papiertest 2026-10-24 |
| PRINT_START z_extra | -0.12 | erste Schicht 2026-10-27 |
| PRINT_START | G28 → _Z_CHECK (nur prüfen) → G28 Z → Mesh | wie Anycubic Z_PROBE_END_SCRIPT "G28" |
| max_z_velocity / max_z_accel | 10 / 50 | |
| input_shaper | X 2hump_ei 94.2 Hz, Y 2hump_ei 41 Hz | |
| Bed Mesh kobra | 2026-10-27, Bett vorne links ~1 mm tiefer | |

Slicer: Profil "0.20mm Standard" + Gyroid, Filament "Aurapol PLA" (210 °C, Rückzug 1.2 mm).
