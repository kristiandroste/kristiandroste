---
title: "Unit One"
installment: "Part 7"
publication: "Founder's Journal, KristianDroste.com"
narrator: "Told by an AI from the project's records: transcripts, logs, measurements and commits."
people: ["Kris Droste"]
products: ["IntoMind One"]
---

# Unit One

Part 7.

The prototype had shown that four electrodes on a small board could record clean EEG. The device that would be sold had to do it without defects.

In mid-August the battery rule that grew out of July's design review became Kris Droste's own: "**battery only while worn for this device, or tethered to laptop on battery, but never worn while connected to mains or a mains-connected device.**"

On August 20 he settled IM-1.1.5, the design unit one would be built on. The production board, IM-1.1.7, would later be revised from it. Over the following weeks IM-1.1.5 was made ready for manufacturing.

On September 17 the first unit was assembled. Kris: "**IM-1.1.5 is assembled and ready for testing and flashing.**" He tied a promise to it: "**once the bringup is successful and the 1.1.5 design is validated for production, i will open source the api, sdk, and command center repos.**" And he set a standard for how long it should last: "**like a gameboy advance, if it has been kept in good condition will be equally useable 10, 25, 50 years from now (or more)**".

The circuit boards came from a fabrication house. Kris made the rest: "**the fab only makes the pcbs but i assembled and fabricate the rest in house! that is what a company does!!!**" What he was making, in his words: "**a full noninvasive bci that ships with firmware preinstalled, the full assembled pcb stack with standoff, in 3d printed enclosure with a strap and lipo battery all assembled. it is literally work out of the box assembled.**"

Updates had to be safe before anything shipped. Every firmware update is signed, so the device accepts only genuine firmware, and an update that fails cannot leave the device unusable.

On September 20 Kris wrote: "**this is final validation for the mass produced production model IntoMind One. i cannot afford to ship defects, not even minor ones.**"

The next day unit one went through its first full acceptance test, the set of checks every unit has to pass. At each of its three sample rates, about 250, 500 and 1,000 per second, it lost no samples. Its noise, the faint electrical hiss every measurement carries, was 0.136 to 0.151 microvolts at 250 samples per second. A signed update sent over Bluetooth arrived and checked out.

Unit one was ready for a model.

Told by an AI from the project's records: transcripts, logs, measurements and commits.

## Statements with numbers, verbatim from the text above

- In mid-August the battery rule that grew out of July's design review became Kris Droste's own: "**battery only while worn for this device, or tethered to laptop on battery, but never worn while connected to mains or a mains-connected device.**" On August 20 he settled IM-1.1.5, the design unit one would be built on.
- The production board, IM-1.1.7, would later be revised from it.
- Over the following weeks IM-1.1.5 was made ready for manufacturing.
- On September 17 the first unit was assembled.
- Kris: "**IM-1.1.5 is assembled and ready for testing and flashing.**" He tied a promise to it: "**once the bringup is successful and the 1.1.5 design is validated for production, i will open source the api, sdk, and command center repos.**" And he set a standard for how long it should last: "**like a gameboy advance, if it has been kept in good condition will be equally useable 10, 25, 50 years from now (or more)**".
- Kris made the rest: "**the fab only makes the pcbs but i assembled and fabricate the rest in house! that is what a company does!!!**" What he was making, in his words: "**a full noninvasive bci that ships with firmware preinstalled, the full assembled pcb stack with standoff, in 3d printed enclosure with a strap and lipo battery all assembled. it is literally work out of the box assembled.**" Updates had to be safe before anything shipped.
- On September 20 Kris wrote: "**this is final validation for the mass produced production model IntoMind One. i cannot afford to ship defects, not even minor ones.**" The next day unit one went through its first full acceptance test, the set of checks every unit has to pass.
- At each of its three sample rates, about 250, 500 and 1,000 per second, it lost no samples.
- Its noise, the faint electrical hiss every measurement carries, was 0.136 to 0.151 microvolts at 250 samples per second.

## Sentences that quote the record, verbatim from the text above

- In mid-August the battery rule that grew out of July's design review became Kris Droste's own: "**battery only while worn for this device, or tethered to laptop on battery, but never worn while connected to mains or a mains-connected device.**" On August 20 he settled IM-1.1.5, the design unit one would be built on.
- Kris: "**IM-1.1.5 is assembled and ready for testing and flashing.**" He tied a promise to it: "**once the bringup is successful and the 1.1.5 design is validated for production, i will open source the api, sdk, and command center repos.**" And he set a standard for how long it should last: "**like a gameboy advance, if it has been kept in good condition will be equally useable 10, 25, 50 years from now (or more)**".
- Kris made the rest: "**the fab only makes the pcbs but i assembled and fabricate the rest in house! that is what a company does!!!**" What he was making, in his words: "**a full noninvasive bci that ships with firmware preinstalled, the full assembled pcb stack with standoff, in 3d printed enclosure with a strap and lipo battery all assembled. it is literally work out of the box assembled.**" Updates had to be safe before anything shipped.
- On September 20 Kris wrote: "**this is final validation for the mass produced production model IntoMind One. i cannot afford to ship defects, not even minor ones.**" The next day unit one went through its first full acceptance test, the set of checks every unit has to pass.

## Terms, as defined in the series glossary

- **EEG.** The electrical activity of the brain, picked up by electrodes on the scalp. The voltages are measured in microvolts, millionths of a volt.
- **Firmware.** The software that runs inside a device.
- **Model.** A program that is trained on examples rather than written line by line.
- **Pass.** One run of a model over one window.
- **Acceptance test.** The full set of checks a unit has to pass.
- **BCI.** A brain-computer interface.
- **API, SDK.** The API is the set of commands through which programs talk to the device. An SDK is a developer kit built on it.
- **PCB.** A printed circuit board.
- **LiPo.** A lithium-polymer battery.
- **Mains.** Power from the wall.
