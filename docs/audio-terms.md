# Audio Terminology & Glossary

A comprehensive reference guide to common audio concepts, connections, and terminology used in live audio production.

---

## Connectors

Understanding the physical connectors is the foundation for understanding audio signal flow. The same connector type can carry different kinds of signals depending on how it's wired.

### XLR (Cannon Connector)

- **3-pin**: Most common for balanced audio
- Professional standard for microphones
- **Male**: Output (microphones, console outputs)
- **Female**: Input (console inputs, powered speakers)
- Locking connector - won't pull out accidentally

```
XLR Balanced Audio (3-pin):
     ___
    /   \     Pin 1: Ground/Shield
   | 2 1 |    Pin 2: Hot (+)
    \ 3 /     Pin 3: Cold (-)
     ---
```

### 1/4" Phone/TRS Connectors

These connectors are extremely versatile. The **same physical connector** can carry different signal types depending on how it's wired!

**TS (Tip-Sleeve)**

- Two conductors (unbalanced)
- Used for: Instrument cables, patch bays, unbalanced line connections
- Also called: Phono plug, guitar cable connector

```
TS - Unbalanced Mono:
    _______________
   |______^|_______|
      Tip   Sleeve
       |      |
    Signal  Ground
```

**TRS (Tip-Ring-Sleeve)**

- Three conductors (can be balanced **OR** stereo)
- Used for: Balanced line connections, headphones (stereo), insert cables

**IMPORTANT**: The same TRS connector is used for two completely different purposes:

```
    TRS - Balanced Mono:            TRS - Stereo Unbalanced:
    ___________________               ___________________
   |____^|_____|_______|             |____^|_____|_______|
     Tip  Ring  Sleeve                 Tip  Ring  Sleeve
      |     |      |                    |     |      |
     Hot  Cold  Ground                Left Right  Ground
     (+)   (-)                        (L)   (R)

Example: XLR to TRS adapter       Example: Headphones
for balanced line-level           carrying stereo audio
```

The key difference:

- **Balanced Mono**: Tip and Ring carry the same signal with opposite polarity
- **Stereo**: Tip and Ring carry two independent signals (left and right channels)

**TRRS (Tip-Ring-Ring-Sleeve)**

- Four conductors
- Used for: Headsets with microphones, smartphone audio
- Commonly used with phones/computers which support a headphone jack

```
TRRS - Headset with Mic:
    _________________________
   |____^|_____|_____|_______|
     Tip  Ring1 Ring2 Sleeve
      |     |     |      |
    Left  Right  Mic  Ground
```

### RCA

- Unbalanced consumer-level connector
- Red/White pairs (stereo)
- Common on consumer playback devices
- Not ideal for professional theatre use

```
RCA - Unbalanced:
     ___
    | | | Center pin: Signal
    |___| Outer ring: Ground
```

### Speakon

- Locking speaker connector (Neutrik brand)
- Used exclusively for speaker connections
- More reliable than 1/4" for high-power applications
- Various configurations (2-pole, 4-pole, 8-pole)

### 3.5mm (1/8") Mini Jack

- Smaller version of 1/4" connector
- TRS configuration for stereo
- Common for: Smartphones, laptops, consumer devices, in-ear monitors
- Often used with adapters in professional settings
- **Same wiring principles as 1/4" TRS** (can be stereo or balanced mono)

### Dante/Ethercon

- RJ45/Ethernet connector for digital audio networking
- Locking version (Ethercon) preferred for stage use
- Carries multiple audio channels over Cat5e/Cat6 cable

---

## Signal Types

Now that you understand the physical connectors, let's explore the different types of signals they carry.

### Balanced vs. Unbalanced

Now that you've seen the connectors above, here's how signals flow through them:

**Balanced** signals use three conductors (positive, negative, and ground) to carry audio. The signal is sent on two wires with opposite polarity, which allows interference picked up along the cable to be canceled out at the receiving end. This provides better noise rejection and allows for longer cable runs. Common in professional audio.

- **Connectors**: XLR (3-pin), TRS (balanced mono configuration)
- **Example**: Microphone → XLR cable → Mixer

**Unbalanced** signals use two conductors (signal and ground). More susceptible to electromagnetic interference and noise, especially over longer distances. Typically limited to runs under 20 feet in professional settings.

- **Connectors**: TS, RCA, TRS (stereo configuration uses unbalanced signals)  
- **Example**: Guitar → TS cable → Amplifier

### Signal Levels

**Mic Level** (-60 to -40 dBu)

- The weakest audio signal, produced by microphones
- Requires pre-amplification before mixing or processing
- Very sensitive to noise and interference

**Line Level** (-10 dBV or +4 dBu)

- Standard operating level for most audio equipment
- **-10 dBV**: Consumer/prosumer equipment (unbalanced)
- **+4 dBu**: Professional equipment (balanced)
- Approximately 10-12 dB difference between the two standards

**Instrument Level**

- Between mic and line level
- Typical output from electric guitars and basses
- Requires DI (Direct Input) box to convert to mic/line level

**Speaker Level**

- High-power amplified signal from power amplifiers
- Designed to drive loudspeakers
- Never connect speaker-level outputs to line-level inputs!

---

## Connections & Cables

Understanding how cables are wired internally helps explain why certain connectors work for balanced vs. unbalanced signals (see [Connectors](#connectors) above).

### Balanced Connections

Use three conductors to provide noise rejection:

- **Hot (Positive)**: Carries the audio signal
- **Cold (Negative)**: Carries inverted audio signal  
- **Ground (Shield)**: Provides grounding and shielding

Best for: Long cable runs, stage-to-booth connections, mic cables

**See the XLR and TRS (balanced mono) diagrams above for wiring details.**

### Unbalanced Connections

Use two conductors:

- **Tip**: Carries the audio signal
- **Sleeve**: Ground/shield

Best for: Short connections, patch bays, instrument cables

**See the TS and RCA diagrams above for wiring details.**

### Cable Types

**Mic Cable**

- Uses XLR or TRS (balanced mono) connectors
- Balanced connection - three conductors
- Typically 20-100 feet in theatre applications
- Quality matters - cheap cables add noise

**Instrument Cable**

- Uses TS connectors  
- Unbalanced connection - two conductors
- For guitars, basses, keyboards
- Keep runs short (under 20 feet when possible)

**Speaker Cable**

- Uses Speakon or 1/4\" TS connectors (high-power rated)
- Heavy gauge wire to carry amplified signals
- Never use for mic or line-level signals
- Not interchangeable with instrument cables

**Snake/Multicore**

- Multiple channels in one cable bundle
- Typically uses XLR connections at each end
- Stage box to mixing console connection
- Can be analog or digital

---

## Equipment Terms

### DI Box (Direct Input/Direct Injection)

Converts unbalanced, high-impedance instrument signals to balanced, low-impedance mic-level signals. Essential for connecting guitars, keyboards, and other instruments to the mixer.

**Active DI**: Requires power (battery or phantom power), provides gain
**Passive DI**: No power required, simple transformer-based

### Phantom Power (+48V)

DC voltage sent through mic cables to power condenser microphones and active DI boxes. Safe for dynamic mics but can damage ribbon mics - always check before engaging!

### Preamp/Gain

The input stage that amplifies mic or line-level signals to optimal operating level. Proper gain staging is critical - set gain first, then adjust faders.

### Compressor

Reduces dynamic range by automatically lowering loud signals. Helps keep vocals consistent and prevents distortion.

### EQ (Equalizer)

Adjusts the balance of frequency content in a signal. Used to:

- Reduce feedback
- Improve clarity
- Shape tone
- Remove unwanted frequencies

### Gate/Noise Gate

Automatically mutes a channel when the signal falls below a set threshold. Reduces bleed from other sources and background noise.

### Aux Send/Auxiliary Send

Independent mix output from the console used for:

- **Stage monitors**: Pre-fader sends
- **Effects** (reverb, delay): Post-fader sends
- **Recording feeds**: Pre or post-fader

### Main/Master Fader

Controls the overall output level of the main mix going to the house speakers.

### Group/Bus

Submix that combines multiple channels, allowing control of several inputs with one fader. Example: All choir mics on one group.

### Matrix

Output that can combine multiple buses/mains in custom ratios. Used for: Fill speakers, delay towers, lobby feeds.

---

## Mixing Concepts

### Gain Staging

The process of setting proper signal levels at each stage of the audio chain:

1. Set input gain (preamp) so meters show healthy signal without clipping
2. Adjust channel faders for balance
3. Set master fader to unity (0 dB) or slightly below

### Feedback

The howling/squealing sound when amplified sound from speakers re-enters a microphone and creates a loop. Controlled by:

- Proper mic placement and technique
- EQ (notching out feedback frequencies)
- Reducing monitor/speaker volume
- Using directional microphones

### Headroom

The difference between the normal operating level and the maximum level before clipping/distortion. Always leave headroom to prevent distortion during unexpected peaks.

### Phase

The timing relationship between two audio signals:

- **In Phase**: Signals reinforce each other (louder)
- **Out of Phase**: Signals cancel each other (quieter)
- Common issue with multiple mics on one source

### High-Pass Filter (HPF) / Low-Cut Filter

Removes low frequencies below a set point (typically 80-100 Hz). Essential for:

- Reducing rumble and handling noise
- Minimizing stage vibrations
- Cleaning up vocal mics

### Channel Strip

The collection of controls for a single input: gain, EQ, aux sends, pan, fader, etc.

### Unity Gain (0 dB)

The reference level where no gain or attenuation is applied. Faders marked "0" or "U" are at unity.

---

## Acoustic Terms

### Feedback Frequency

The specific pitch at which feedback occurs. Can be identified and reduced with precise EQ adjustment.

### Frequency Range

- **Sub-bass**: 20-60 Hz (felt more than heard, rumble)
- **Bass**: 60-250 Hz (warmth, body, power)
- **Low Mids**: 250-500 Hz (can be muddy if excessive)
- **Mids**: 500 Hz-2 kHz (presence, voice fundamentals)
- **Upper Mids**: 2-4 kHz (clarity, intelligibility)
- **Presence**: 4-6 kHz (articulation, edge)
- **Brilliance**: 6-20 kHz (air, sparkle, sibilance)

### Proximity Effect

Bass boost that occurs when a directional microphone is used very close to the source. Common with vocals on cardioid mics.

### Room Modes/Standing Waves

Resonant frequencies in a room caused by reflections between parallel surfaces. Can cause uneven bass response.

### Reverberation (Reverb)

The persistence of sound after the source stops, caused by reflections in a space. Adds depth and space to dry signals.

### Delay/Echo

Distinct repetition of sound. Used for:

- Creative effects
- Timing synchronization (delay towers)
- Depth and space

---

## Digital Audio

### Sample Rate

How many times per second digital audio is measured (e.g., 48 kHz = 48,000 samples per second). Higher = better quality but larger file sizes.

- **44.1 kHz**: CD quality
- **48 kHz**: Professional video/broadcast standard (most common in theatre)
- **96 kHz**: High-resolution audio

### Bit Depth

The number of bits used for each audio sample. Determines dynamic range:

- **16-bit**: CD quality (96 dB dynamic range)
- **24-bit**: Professional standard (144 dB dynamic range)
- **32-bit float**: Maximum headroom, virtually impossible to clip

### Latency

The delay between input and output in digital systems. Critical for:

- Live monitoring (musicians need <10ms)
- Digital mixing consoles
- Wireless systems

### Dante

Audio networking protocol that carries multiple channels of audio over standard Ethernet. Used extensively in modern theatre installations.

### Word Clock

Synchronization signal that keeps digital audio devices operating at exactly the same sample rate. Prevents clicks, pops, and audio drift.

### A/D Converter (Analog-to-Digital)

Converts analog audio signals (microphones, instruments) to digital data for processing.

### D/A Converter (Digital-to-Analog)

Converts digital audio back to analog signals to drive speakers and headphones.

---

## Quick Reference Tables

### Common Connector Summary

| Connector | Type | Use Case |
|-----------|------|----------|
| XLR (3-pin) | Balanced | Microphones, professional line connections |
| 1/4" TRS | Balanced/Stereo | Balanced line, headphones, inserts |
| 1/4" TS | Unbalanced | Instrument cables, patch bays |
| 3.5mm TRS | Stereo/Balanced | Consumer devices, IEM, computer audio |
| RCA | Unbalanced | Consumer playback devices |
| Speakon | Speaker | Powered speaker connections |
| Ethercon/RJ45 | Digital | Network audio (Dante, etc.) |

### Signal Flow Reminder

```
Microphone → Mic Cable (XLR) → Mixer Input (Preamp/Gain) → 
Channel Strip (EQ, Dynamics) → Fader → Master Bus → 
Output → Power Amp/Powered Speaker → Audience
```

---

## Tips for Success

1. **Always start with gain, not faders**: Set input gain properly first
2. **Label everything**: Cables, channels, connections
3. **Use balanced connections** whenever possible for better noise rejection
4. **Keep cable runs neat**: Reduces noise and trip hazards
5. **Don't coil cables too tightly**: Damages the conductors and shielding
6. **Check phantom power**: Before connecting ribbon mics or devices that don't need it
7. **High-pass everything**: Except bass instruments and kick drums
8. **Less is more with EQ**: Cut before boost
9. **Ring out monitors properly**: Before rehearsal to prevent feedback
10. **Document your setup**: Makes next time easier

---

## See Also

- [Audio House System](audio-house.md) - Main theatre audio equipment
- [Audio Mobile Setup](audio-mobile.md) - Portable audio systems
- [Audio Vocal Tuning](audio-vocal-tuning.md) - Microphone and vocal mixing techniques
- [Audio Room Tuning](audio-room-tuning.md) - Acoustic optimization