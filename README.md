# Electronic Thermometer — Analog / Mixed-Signal PCB (KiCad)

A discrete **electronic thermometer** designed as a multi-sheet schematic and PCB
in KiCad. The design senses temperature, conditions the signal, drives a coloured
LED step display across temperature bands, and triggers an alarm outside a set
range.

Coursework project for *Elements of Integrated Circuits (LoIC)* at TU Chemnitz.

## Signal chain

| Stage | Sheet | Function |
|-------|-------|----------|
| Temperature sensor | `LM235_Temp_Sensor.kicad_sch` | LM235 sensor produces a temperature-proportional voltage |
| Signal conditioning | `OP_AMPLIFIER.kicad_sch` | LM358 op-amp scales/offsets the sensor signal |
| Level decoding / display | `LED_STEP_DECODER.kicad_sch` | Lights RED / GREEN / BLUE LED steps for temperature bands |
| Timing / alarm | `ALARM_SUBSYSTEM.kicad_sch`, `AL-P060I.kicad_sch` | NE555 gated oscillator + transistor stage drive an out-of-range alarm |
| Top sheet + PCB | `ET_OLD.kicad_sch`, `ET_OLD.kicad_pcb` | Hierarchical top level and routed board |

A transient simulation (see `images/`) shows the RGB step outputs handing over
across the temperature sweep and the alarm asserting outside the valid band.

## Repository contents

- `ET_OLD.kicad_pro` — open this in KiCad to load the whole project
- `*.kicad_sch` — hierarchical schematic sheets
- `ET_OLD.kicad_pcb` — routed PCB layout
- `*.lib` — component symbol libraries used by the design
- `images/` — schematic overview, PCB layout, and simulation screenshots

> Requires KiCad (designed in KiCad 10). Open `ET_OLD.kicad_pro`.

## Skills demonstrated
Analog + mixed-signal design · sensor signal conditioning (op-amps) · 555 timer
circuits · hierarchical schematic capture · PCB layout & routing · KiCad

## Preview

![Schematic overview](images/schematic_overview.png)
![PCB layout](images/pcb_layout_1.png)
