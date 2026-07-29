# Enigma HTML Teaching Apps

This repository contains two standalone HTML teaching apps for exploring simplified Enigma machines and software-based cryptanalysis demonstrations.

Both apps are written in plain HTML, CSS, and JavaScript. No build step is required. Open the corresponding `.html` file directly in a browser, or publish the repository with GitHub Pages.

## Overview

### Single-Rotor Version

The single-rotor app introduces the basic signal path of a simplified Enigma-style machine:

- Keyboard, lampboard, plugboard, Rotor I, and Reflector B
- Optional rotor stepping
- On-screen keyboard input and physical keyboard capture
- Animated signal-path tracing for each letter
- Batch text encryption
- Before/after letter-frequency distributions
- A `Principles` tab explaining the plugboard, rotor, reflector, crib, menu, loop, and stop
- A `Modern Crack` tab demonstrating a modern IC and language-statistics attack
- A `The Bombe` tab demonstrating crib/menu constraint propagation

### Two-Rotor Version

The two-rotor app extends the teaching model to two rotors:

- Rotor I is the fast rotor
- Rotor II is the slow rotor
- Rotor I steps before each encrypted letter
- Rotor II steps when Rotor I returns to `A`
- Reflector B remains fixed
- English/Chinese UI switching
- Editable ciphertext for attack experiments
- A `Modern Crack` tab for two-rotor ciphertext-only search
- A `The Bombe` tab showing crib dragging, loop menus, stops, language ranking, and word-clue refinement

## Default Plaintext and Ciphertexts

Both apps use the same default teaching plaintext:

```text
TO NORTH STAR: WEATHER WINDOW OPENS AT DAWN. MOVE THE FIELD RADIO TO THE OLD MILL AND WAIT FOR THE GREEN LAMP SIGNAL. SUPPLIES ARRIVE BY RIVER AT NINETEEN HUNDRED HOURS. ACKNOWLEDGE WITH THE WORD LANTERN.
```

The default ciphertexts are different because the machine models are different:

- The single-rotor version uses one Rotor I.
- The two-rotor version uses Rotor I and Rotor II.
- Both versions use the default plugboard pairs `A↔M F↔I N↔V P↔S T↔U`.

## Language Model

The modern attack and Bombe ranking stages use an English quadgram frequency model. The pages attempt to load a default public quadgram table automatically, and users may also upload a compatible custom model.

The model file should contain one four-letter group and one count per line, for example:

```text
TION 12345
THER 9876
```

If browser or network restrictions block automatic loading, download the default model from the link shown inside the app and select it manually with the file picker.

## Teaching Scope

These apps are teaching demonstrations. They are not complete reproductions of historical Enigma machines or historical Bombe hardware.

- The machine models are simplified so that the signal path and constraint logic are visible.
- The single-rotor version is not a historical military Enigma.
- The two-rotor version demonstrates a larger rotor-state space and staged elimination logic, but it is still a simplified model.
- `Modern Crack` uses modern language-statistics scoring as a teaching aid; it does not represent the historical Bombe reading plaintext automatically.
- `The Bombe` demonstrates crib/menu/loop/stop constraint propagation and then uses modern ranking and word-clue refinement to make the later analysis easier to inspect.

## References

- [Cipher Machines & Cryptology](https://www.ciphermachinesandcryptology.com/index.htm)
- [GCHQ CyberChef: Enigma, the Bombe, and Typex](https://github.com/gchq/CyberChef/wiki/Enigma,-the-Bombe,-and-Typex)
- [YouTube: Enigma and the Bombe](https://www.youtube.com/watch?v=ybkkiGtJmkM)

## Copyright

Developed by Dr. Yongxin Liu, Embry-Riddle Aeronautical University.
