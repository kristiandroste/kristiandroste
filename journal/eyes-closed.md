---
title: "Eyes Closed"
installment: "Part 5"
publication: "Founder's Journal, KristianDroste.com"
narrator: "Told by an AI from the project's records: transcripts, logs, measurements and commits."
people: ["Kris Droste"]
products: []
---

# Eyes Closed

Part 5.

In early August the only IM-1.0 board went dark again.

On August 4 a fault was found in the board that measures the electrodes: a short circuit of 0.3 ohms, an unintended connection between two of its power lines, present in the board as it was made. Kris Droste fixed it by cutting the copper at a point worked out in advance: "**cut is done**", then "**all pass**".

The next day the ADS1299 answered every request with zeros, and the AI concluded that the chip's data input was dead. That evening a diagnostic build of the firmware held one of the processor's pins on for minutes. The board survived it. The AI then blamed that pin instead and drew a cut in a copper line on the processor board to work around it. Kris refused: "**this needs to be a sure shot thing before i cut the line. because once i cut it there is no going back.**"

Minutes later, at the first power-up after Kris had washed the board with solvent, it went dark. Measurement found a film of residue left by the wash, conducting at 14.3 ohms and bridging the digital supply to ground at the connector between the two boards. The record rules out the diagnostic build as the cause.

Kris began to think about a new board: "**i am at the point where i think a final version pcb spinup might be the best option, instead of performing more board surgery.**"

On August 12 the board came back. Once the film was cleaned away, the debug port answered again, and part of the processor's memory turned out to be erased. The cause was never found. Reloaded, the processor came back: USB, Bluetooth and the debug port all answered. That morning Kris also cleaned a residue off the measuring board.

The ADS1299 was the remaining question. The AI's verdict was now that the chip itself was damaged. Kris did not accept it: "**i dont think the chip is damaged. i think there is some other cause or maybe some inaccurate measurement.**" On August 13 the chip reported ready on every one of seven starts. It passed all 37 of its acceptance checks, the tests a board has to pass. Its sample rates measured 250.00, 500.00 and 1000.01 per second. With its inputs connected together, so that it measured only its own noise, its noise was 0.133 to 0.142 microvolts, the floor given in its datasheet. The data input had never been dead.

Next came the parts that make a device wearable: "**now lets fix the battery charging and power swtich so that the device can actually sit in its enclosure and become a true wearable.**" Kris reworked the power switch so that off meant off, removed a part that had been keeping the battery from charging, and fitted a 500 milliamp-hour battery. On August 14 the board ran on its own battery and streamed live into the Command Center, IntoMind's app for viewing and recording the signal.

The enclosure closed around it. Kris on what users want: "**they want seamless interface and total abstraction of all internal parts: they want a usb port and a power switch, with no leaks to the inside of the enclosure.**"

Then he asked: "**is it recording proper, clean eeg?**"

August 16 answered in steps. The board's built-in test signal measured exactly 1.9531 cycles per second. A known external signal of about 280 microvolts read between 248 and 255 on all four channels. With the inputs shorted, the noise floor was 0.134 to 0.137 microvolts.

Then Kris strapped it on, in its freshly printed enclosure, on battery, sending everything over Bluetooth. With his eyes closed, the alpha rhythm appeared in all 8 eyes-closed blocks of recording, three to nine times stronger than the surrounding signal. With his eyes open, it collapsed. Not one sample was lost. Alpha is a rhythm of about ten cycles per second that strengthens when the eyes close.

Kris asked for the day to be written down: "**write up a factual narrative of my journey with this device up to this triumphant point, save it, and commit.**"

IM-1.0 worked. It would not be the design that went into production.

Told by an AI from the project's records: transcripts, logs, measurements and commits.

## Statements with numbers, verbatim from the text above

- In early August the only IM-1.0 board went dark again.
- On August 4 a fault was found in the board that measures the electrodes: a short circuit of 0.3 ohms, an unintended connection between two of its power lines, present in the board as it was made.
- The next day the ADS1299 answered every request with zeros, and the AI concluded that the chip's data input was dead.
- Measurement found a film of residue left by the wash, conducting at 14.3 ohms and bridging the digital supply to ground at the connector between the two boards.
- Kris began to think about a new board: "**i am at the point where i think a final version pcb spinup might be the best option, instead of performing more board surgery.**" On August 12 the board came back.
- The ADS1299 was the remaining question.
- Kris did not accept it: "**i dont think the chip is damaged. i think there is some other cause or maybe some inaccurate measurement.**" On August 13 the chip reported ready on every one of seven starts.
- It passed all 37 of its acceptance checks, the tests a board has to pass.
- Its sample rates measured 250.00, 500.00 and 1000.01 per second.
- With its inputs connected together, so that it measured only its own noise, its noise was 0.133 to 0.142 microvolts, the floor given in its datasheet.
- Next came the parts that make a device wearable: "**now lets fix the battery charging and power swtich so that the device can actually sit in its enclosure and become a true wearable.**" Kris reworked the power switch so that off meant off, removed a part that had been keeping the battery from charging, and fitted a 500 milliamp-hour battery.
- On August 14 the board ran on its own battery and streamed live into the Command Center, IntoMind's app for viewing and recording the signal.
- Kris on what users want: "**they want seamless interface and total abstraction of all internal parts: they want a usb port and a power switch, with no leaks to the inside of the enclosure.**" Then he asked: "**is it recording proper, clean eeg?**" August 16 answered in steps.
- The board's built-in test signal measured exactly 1.9531 cycles per second.
- A known external signal of about 280 microvolts read between 248 and 255 on all four channels.
- With the inputs shorted, the noise floor was 0.134 to 0.137 microvolts.
- With his eyes closed, the alpha rhythm appeared in all 8 eyes-closed blocks of recording, three to nine times stronger than the surrounding signal.
- Kris asked for the day to be written down: "**write up a factual narrative of my journey with this device up to this triumphant point, save it, and commit.**" IM-1.0 worked.

## Sentences that quote the record, verbatim from the text above

- Kris Droste fixed it by cutting the copper at a point worked out in advance: "**cut is done**", then "**all pass**".
- Kris refused: "**this needs to be a sure shot thing before i cut the line. because once i cut it there is no going back.**" Minutes later, at the first power-up after Kris had washed the board with solvent, it went dark.
- Kris began to think about a new board: "**i am at the point where i think a final version pcb spinup might be the best option, instead of performing more board surgery.**" On August 12 the board came back.
- Kris did not accept it: "**i dont think the chip is damaged. i think there is some other cause or maybe some inaccurate measurement.**" On August 13 the chip reported ready on every one of seven starts.
- Next came the parts that make a device wearable: "**now lets fix the battery charging and power swtich so that the device can actually sit in its enclosure and become a true wearable.**" Kris reworked the power switch so that off meant off, removed a part that had been keeping the battery from charging, and fitted a 500 milliamp-hour battery.
- Kris on what users want: "**they want seamless interface and total abstraction of all internal parts: they want a usb port and a power switch, with no leaks to the inside of the enclosure.**" Then he asked: "**is it recording proper, clean eeg?**" August 16 answered in steps.
- Kris asked for the day to be written down: "**write up a factual narrative of my journey with this device up to this triumphant point, save it, and commit.**" IM-1.0 worked.

## Terms, as defined in the series glossary

- **EEG.** The electrical activity of the brain, picked up by electrodes on the scalp. The voltages are measured in microvolts, millionths of a volt.
- **ADS1299.** The chip in the IntoMind One that measures the electrodes and turns each measurement into a number. It is an ADC, the kind of chip that turns an analog voltage into digital numbers.
- **Firmware.** The software that runs inside a device.
- **Pass.** One run of a model over one window.
- **Noise floor.** The level of a measuring chip's own electrical noise, below which it cannot see a signal.
- **Datasheet.** The manufacturer's document that specifies a chip.
- **Short circuit.** An unintended electrical connection.
- **PCB.** A printed circuit board.
