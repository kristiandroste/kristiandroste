---
title: "The Only Board"
installment: "Part 2"
publication: "Founder's Journal, KristianDroste.com"
narrator: "Told by an AI from the project's records: transcripts, logs, measurements and commits."
people: ["Kris Droste"]
products: ["IntoMind One"]
---

# The Only Board

Part 2.

The IntoMind One's enclosure came early. The earliest enclosure file on Kris Droste's computer is a 3D model dated December 12, 2025. By the end of May 2026 the design had reached a version saved as "FINAL-V1.1", and every IntoMind One enclosure since has been derived from those shells.

IM-1.0, the first prototype of the electronics, is two round circuit boards stacked one on the other. One carries the processor with its Bluetooth radio, the charging circuit and a USB-C port. The other carries the ADS1299, the chip that measures the electrodes, and the connections for four electrodes and a reference in a single cluster. The boards were made from manufacturing files dated May 23, 2026, and Kris soldered every component onto them himself: "**i soldered all of the components myself.**"

On July 3 he turned to the software: "**this device is fully fabbed and assembled. now i need the firmware and tests.**" The AI he was working with started building right away. About an hour later he stopped it: "**this is a consumer bci product. you jumped the gun by going straight to building. archive what you just built, and lets start over, this time architecting comprehensively for the ultimate end user experience before building anything.**" A BCI is a brain-computer interface.

That day he set down what the product had to be. Users would own their data: "**i want users to have completely free, private, open access to their own data--complete neural data sovereignty.**" Every sample would carry its time from the device itself. And a lost sample would never be hidden: "**the crucial thing for managing dropped samples is that they get tagged as dropped and dont silently contaminate the timeseries data.**"

Before the board was powered, checks of every connection turned up a wiring fault: the power switch was connected so that turning it off would short-circuit the power supply. Then came the first loading of the device's firmware. Hours later the board stopped answering, over USB, over Bluetooth and through its debug port, a wired connection for programming and testing the processor. Kris: "**there is no other bci board. this is the only one in existence, the only and first one ever made.**"

The AI's first explanation was that loading the firmware had locked the chip. It was wrong, and it was withdrawn at the end of the month. In the meantime the board stayed dark for three weeks, and Kris set the rules for getting it back: no new purchases, and almost no soldering. He did not believe the chip had failed: "**good silicon like our module doesnt just go dead.**"

While the board was dark, the whole design was reviewed part by part, beginning on July 5. One rule that came out of the review is still in the product: when the device is worn, it runs on battery only.

The answer turned up on July 30. Measurements had already found a leak of a few ohms, nearly a short circuit, on the circuits of both of the board's buttons. Cold spray, a quick-freezing aerosol, pointed to the reset button. Kris asked whether removing the button would settle the question, then took it off with hot air. The board booted at once. A solder defect hidden inside the button had kept the processor stuck in its reset state, unable to start, since July 5. The chip had been healthy the whole time. Of the button, Kris wrote: "**the button actually came apart layer by layer, so i wonder if they are just poorly made buttons.**"

On July 31, with the board alive again, the rules for how the device talks to a computer passed all 34 of their checks on it. The first entry in the project's code history says it in one line: "board #1 revived, protocol v0.1 validated on-device."

The board's troubles were not over.

Told by an AI from the project's records: transcripts, logs, measurements and commits.

## Statements with numbers, verbatim from the text above

- The earliest enclosure file on Kris Droste's computer is a 3D model dated December 12, 2025.
- By the end of May 2026 the design had reached a version saved as "FINAL-V1.1", and every IntoMind One enclosure since has been derived from those shells.
- IM-1.0, the first prototype of the electronics, is two round circuit boards stacked one on the other.
- The other carries the ADS1299, the chip that measures the electrodes, and the connections for four electrodes and a reference in a single cluster.
- The boards were made from manufacturing files dated May 23, 2026, and Kris soldered every component onto them himself: "**i soldered all of the components myself.**" On July 3 he turned to the software: "**this device is fully fabbed and assembled. now i need the firmware and tests.**" The AI he was working with started building right away.
- He did not believe the chip had failed: "**good silicon like our module doesnt just go dead.**" While the board was dark, the whole design was reviewed part by part, beginning on July 5.
- The answer turned up on July 30.
- A solder defect hidden inside the button had kept the processor stuck in its reset state, unable to start, since July 5.
- Of the button, Kris wrote: "**the button actually came apart layer by layer, so i wonder if they are just poorly made buttons.**" On July 31, with the board alive again, the rules for how the device talks to a computer passed all 34 of their checks on it.
- The first entry in the project's code history says it in one line: "board #1 revived, protocol v0.1 validated on-device." The board's troubles were not over.

## Sentences that quote the record, verbatim from the text above

- By the end of May 2026 the design had reached a version saved as "FINAL-V1.1", and every IntoMind One enclosure since has been derived from those shells.
- The boards were made from manufacturing files dated May 23, 2026, and Kris soldered every component onto them himself: "**i soldered all of the components myself.**" On July 3 he turned to the software: "**this device is fully fabbed and assembled. now i need the firmware and tests.**" The AI he was working with started building right away.
- About an hour later he stopped it: "**this is a consumer bci product. you jumped the gun by going straight to building. archive what you just built, and lets start over, this time architecting comprehensively for the ultimate end user experience before building anything.**" A BCI is a brain-computer interface.
- Users would own their data: "**i want users to have completely free, private, open access to their own data--complete neural data sovereignty.**" Every sample would carry its time from the device itself.
- And a lost sample would never be hidden: "**the crucial thing for managing dropped samples is that they get tagged as dropped and dont silently contaminate the timeseries data.**" Before the board was powered, checks of every connection turned up a wiring fault: the power switch was connected so that turning it off would short-circuit the power supply.
- Kris: "**there is no other bci board. this is the only one in existence, the only and first one ever made.**" The AI's first explanation was that loading the firmware had locked the chip.
- He did not believe the chip had failed: "**good silicon like our module doesnt just go dead.**" While the board was dark, the whole design was reviewed part by part, beginning on July 5.
- Of the button, Kris wrote: "**the button actually came apart layer by layer, so i wonder if they are just poorly made buttons.**" On July 31, with the board alive again, the rules for how the device talks to a computer passed all 34 of their checks on it.
- The first entry in the project's code history says it in one line: "board #1 revived, protocol v0.1 validated on-device." The board's troubles were not over.

## Terms, as defined in the series glossary

- **Electrode, reference.** An electrode is a contact on the scalp. Each electrode's voltage is measured against a reference contact.
- **ADS1299.** The chip in the IntoMind One that measures the electrodes and turns each measurement into a number. It is an ADC, the kind of chip that turns an analog voltage into digital numbers.
- **Firmware.** The software that runs inside a device.
- **Model.** A program that is trained on examples rather than written line by line.
- **Short circuit.** An unintended electrical connection.
- **BCI.** A brain-computer interface.
