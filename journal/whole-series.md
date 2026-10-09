# Founder's Journal

*How the IntoMind One and the IntoMind Mu models were built, from the project's records.*

## Fourteen Seconds

*Prologue*

On the morning of September 26, 2026, unit one was streaming to a laptop with its model switched on.

Unit one was the first IntoMind One, a wearable EEG device, that Kris Droste had built for validation. EEG is the electrical activity of the brain, picked up by electrodes resting on the scalp. The voltages are tiny, measured in millionths of a volt. The IntoMind One has four electrodes and a reference. It has an ADS1299, a chip that measures the electrodes 250, 500 or 1,000 times a second and turns each measurement into a number. And it has an nRF52840, a small processor with a Bluetooth radio that runs the device.

The model ran on that processor. A model, in this sense, is a program that is not written line by line. It is trained, shown example after example until the numbers inside it, its parameters, capture the patterns in the examples. This one took four seconds of signal at a time, measured 500 times a second, and turned each window into 96 numbers that describe it. The device sent those numbers to the laptop alongside the signal itself.

It had 491,904 parameters. It was a student, distilled from a much larger teacher: a model of 17.8 million parameters that had learned from 3,814 hours of public EEG recorded by other labs. Distillation means training the small model to reproduce what the large one says about each window. Later the student would be named Mu 492K.

Eight days earlier, the AI working with Kris had recommended a safer launch: run the model on the user's computer and keep it out of the firmware, the software inside the device. Kris refused: "**the model is tiny and fits on a chip precisely for the reason of fitting it on a chip.**"

Now it was on the chip, and it was slow. A window fills in four seconds. To keep up, the model has to finish each window before the next one is ready. That morning it needed about 14 seconds. Even working without pause, the chip could describe only one window in four.

Kris was not asking the model to do everything. That same morning he wrote: "**it doesnt need to do everything for everyone at launch. it just needs to have well defined utility and limitations.**"

How a model like this came to be on a chip like that had begun months earlier, on two tracks that had not yet met: a prototype board that Kris assembled himself, and a collection of other people's EEG.

## Other People's EEG

*Part 1*

The models in the IntoMind One learned from people who never wore one. Their EEG came from OpenNeuro, a free public archive where neuroscience labs share the data behind their studies.

On March 17, 2026, a program began reading that archive for Kris Droste. It scanned 1,660 of the 1,666 datasets on OpenNeuro and found 390 that held EEG. Downloads ran until March 30, capped at 50 gigabytes per dataset, so 86 datasets that qualified but were larger than that were never fetched.

The goal was there from the start. By March 31 the project's own description of itself said it was "building neural signal foundation models". A foundation model is a model trained on a great deal of data without labels, to learn the general structure of that data, so that it can later be put to many uses.

Other people's EEG is not one thing. Each lab chooses its own equipment, its own number of electrodes, its own names for where they sit on the head and its own rate of measurement. Each describes its participants in its own words. Before the recordings could be used together, they had to be put into one form. The project's instructions set the rules for that work: labels a person can read, no precision the source does not have, and when in doubt, stop and ask Kris.

On April 1 the rules for preparing the data were written down. Recordings would be read at 19 standard positions on the scalp, the positions of the international 10-20 system, and a dataset with fewer than 15 of them was skipped. Only datasets recorded at 500 samples per second or more were used, and everything was brought to 500 and cut into windows of four seconds. No recording would be cleaned of artifacts, the parts of a recording that are not brain activity, and no missing electrode would be filled in. The record holds no reasons for these choices. The project's own fact record later noted that they had been "specified by fiat in a single message". The four-second window and the 500 samples per second that the IntoMind One's model uses today trace back to them.

The first experiments came two days later. The usual way to summarize EEG is band power: how strong each of the brain's rhythms is, from the slow delta rhythm to the fast gamma rhythm. Two of the questions the April experiments asked with it were how those rhythms change across the lifespan and how they differ between women and men. They were among the first checks on the corpus, the collection of recordings, and age, sex and band power would come back again and again.

In April a check of every dataset at its source began. Kris set the standard for it: "**Do not rubber-stamp datasets... The goal is zero unverified datasets in the final corpus, not zero flags in this document.**" By early May, 188 datasets were certified and seven were excluded.

Every analysis so far had looked at EEG through band power. Whether there was more in the signal than band power could see was a question for a different kind of tool.

## The Only Board

*Part 2*

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

## No Fake Data

*Part 3*

On July 18, Kris Droste had a new piece of hardware, a graphics card, and he wanted "**to put it to some good use on this corpus.**" A graphics card, or GPU, is the kind of chip AI models are trained on. This one had 8 gigabytes of memory and sat in an external enclosure, connected by a cable to a small desktop computer with 16 gigabytes of memory. It became the training machine.

The AI working with Kris named the problem it could address. Every analysis so far had run on band power, which "discards phase, cross-channel structure, temporal dynamics, and waveform shape": it keeps how strong each rhythm is and throws away its timing, its shape and how the electrodes move together. A model that learned from the signal itself might see what band power could not. The plan put the corpus right first. Then the GPU work would begin with a test that could not fail quietly, "Brain age first", meaning a check of whether a model could tell a person's age from their EEG. Kris approved the plan: "**this looks good. approved.**" His priority was the data itself: "**what matters is that my data is clean and accurate.**"

What followed was a rebuild of the corpus on rules Kris set one by one.

On artifacts, the parts of a recording that are not brain activity: "**we are removing *mechanical* artifacts, such as electrode disconnections, during which the signal is *absent* by definition, but we are retaining *physiological* 'artifacts' because that is real signal, real eeg.**" A blink is physiological. An electrode coming loose is mechanical.

On purpose: "**i am much more interested in building real time systems with eeg than i am in building post hoc data analysis pipelines.**" Whatever was done to the corpus had to be something a device could do to a live signal.

On sample rates, where upsampling means inventing samples between real ones: "**upsampling is something i will not accept… it truly is foundation building that we are doing.**" For one evening the corpus was set to 250 samples per second. The decision was reversed the same evening, and 500 stood, the highest rate that every dataset in the corpus then reached without inventing samples.

On missing data, where interpolation means filling in a missing electrode by guessing from its neighbors: "**interpolation is and has always been a hard no. absolutely no fake data may enter the corpus.**"

And on who it was all for: "**the models are for the real intomind bci devices.**"

Kris to the AI, on removing duplicate recordings: "**excluded means purge, but nothing unique and fitting our criteria should be excluded… you are an ai engineer and a surgeon with a scalpel, not a lumberjack with a chainsaw**". Seven whole datasets and 458 recordings turned out to be byte-for-byte duplicates and were removed. People who appeared in more than one dataset were matched by each lab's own records, never by guessing from the signal.

On July 27 the rebuilt corpus was finished: 7,116,460 windows of four seconds from about 260 datasets, close to 400 gigabytes, with every value in microvolts.

Next came how to split the data between training and testing for the models to come. Kris proposed keeping each person's recordings together, then added: "**dont agree to something just because i suggested it.**" A measurement decided on a stricter rule: every recording from a study stays on one side of the split. Every model in this story was trained and tested that way.

On July 30 the teacher began to train.

## The Teacher

*Part 4*

The teacher is the largest model in this story: 17.8 million parameters. It learned without labels, that is, without being told anything about the people in the recordings. Each four-second window was cut into short pieces, half of the pieces were hidden, and the model was trained to fill in what was hidden from what was left. To do that well, a model has to capture how EEG behaves.

Training ran on the graphics card from July 30 to July 31: 300,000 training steps, each on 96 windows, 15.9 hours in all. In that time the model saw 28.8 million windows, more than eight passes over 3,432,863 training windows recorded from 4,945 people. Each window covered up to 19 positions on the scalp, and at least 15 had to be working.

There were things it never saw. Recordings made at fewer than 500 samples per second, 30.4 percent of the windows, were left out. And 32.8 million event markers in the recordings, notes of what was happening when, were never read.

While it was still training, Kris Droste asked a question that would shape everything after: "**would this model fit on a nrf52840 in the firmware? and run there realtime?**" The answer was no. It was about 18 times too large and 60 times too slow.

First, though, it had to show that it had learned anything useful. The way to ask is a probe: leave the model unchanged, train a simple linear readout on the numbers it produces, test that readout on studies held out from its training, and run band power through exactly the same test.

The test the AI proposed was age and sex. They are recorded in study after study, and they are facts rather than one lab's judgment: "the labels we have in quantity, across many studies, and they're objective rather than one lab's vocabulary." Kris agreed, with a reminder: "**yes we should definitely test age and sex on the current model ... this is a general purpose foundation model we are building.**"

The results: asked to tell women from men, using one averaged description per person, the readout on the model's numbers scored an AUC of 0.773, against 0.660 for band power, and the model won in 99 of 122 test groups. AUC measures how well a test separates two groups: 0.5 is a coin toss, and 1.0 is perfect. On age, its typical error was 8.52 years, against 9.63 for band power. That difference did not hold up once the number of tests was accounted for, except among adults alone.

Two days later the AI put the situation in one sentence: "the only two things this program can currently measure with real statistical power are age and sex." Statistical power is the ability to detect a real effect. About 150 studies in the corpus recorded each of them, with both sexes or a spread of ages inside the same study.

That is why the IntoMind Mu models are measured on age and sex. Age and sex were never the goal. They were the only questions the public data could answer with confidence.

## Eyes Closed

*Part 5*

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

## The Student

*Part 6*

The teacher was about 18 times too large for the chip in the IntoMind One and about 60 times too slow. Kris Droste asked what the alternative was: "**i mean training the tiny version on its own not as a student. what is the difference?**"

The answer became an experiment. On August 1 Kris set the goal: "**the goal is to build a foundation model that fits on the nrf along with the firmware weve built.**" And the comparison: "**we can compare training it 'from scratch' to training it by distilling the current model.**" The plan written that day describes the model as "A small EEG encoder that fits alongside existing nRF52840 firmware, as a tiny version of the same foundation model", not tied to one placement of the electrodes.

Kris added two demands: "**its supposed to be versatile,**" and "**the device can sit *anywhere* on the head.**" The plan records a third ruling, "EVERYTHING IN THE SIGNAL CHAIN IS CONFIGURABLE", and so the device was set to match the corpus: 500 samples per second and the same filter, which removes slow drift below half a cycle per second.

Could a model work anywhere on the head? The teacher was tested at 24 random placements, eight each with two, four and eight electrodes. With only two electrodes it told women from men with an AUC of 0.644, against 0.574 for band power. With four it scored 0.690 against 0.620, and with eight, 0.741 against 0.642. From one placement to another the scores moved by only 0.04 to 0.06. The plan recorded that this answered "the main risk in the whole approach".

Before any student was trained, the test it had to pass was written down: beat band power on sex and age.

Distillation works like this. The teacher looks at a window recorded at up to 19 positions and sums it up as 384 numbers. The student sees only the few electrodes a device has, two to eight of them, and is trained to produce the teacher's summary of the same window. It learns from information it will never have.

On August 1 six students were trained under the same rules, three from scratch and three by distillation, one of each for three ways of handling the electrode positions: always told where they were, never told, or told half of the time. The students trained from scratch did not beat band power. The distilled ones did. In all 12 comparisons between matching pairs, distillation came out ahead, in 11 of them by more than the margin of error. Telling the student where its electrodes were half of the time worked best. A student that was always told lost 1.24 years of accuracy on age when that information was taken away.

The model chosen had 491,904 parameters. The file the device later loaded for it, with its numbers stored at 8 bits each, is 503,072 bytes. It had been trained once, for 60,000 training steps.

The next day Kris set two directions: "**i want to train to largest model that will train and fit on this gpu, and i want to train tiny models successively down to the smallest model that beats bandpower.**" The large one was never trained. The small ones would be.

That evening Kris asked a plain question: "**wait so what does the little encoder actually do?**" The answer: "It turns 4 seconds of EEG into 96 numbers." It was, in the AI's words, "a feature extractor, not a detector." Those 96 numbers carried a little more than band power did about a person's age and sex. Whatever a user wants from them, a head, a small add-on trained on those numbers, turns them into an answer.

The student would not meet the device until September.

## Unit One

*Part 7*

The prototype had shown that four electrodes on a small board could record clean EEG. The device that would be sold had to do it without defects.

In mid-August the battery rule that grew out of July's design review became Kris Droste's own: "**battery only while worn for this device, or tethered to laptop on battery, but never worn while connected to mains or a mains-connected device.**"

On August 20 he settled IM-1.1.5, the design unit one would be built on. The production board, IM-1.1.7, would later be revised from it. Over the following weeks IM-1.1.5 was made ready for manufacturing.

On September 17 the first unit was assembled. Kris: "**IM-1.1.5 is assembled and ready for testing and flashing.**" He tied a promise to it: "**once the bringup is successful and the 1.1.5 design is validated for production, i will open source the api, sdk, and command center repos.**" And he set a standard for how long it should last: "**like a gameboy advance, if it has been kept in good condition will be equally useable 10, 25, 50 years from now (or more)**".

The circuit boards came from a fabrication house. Kris made the rest: "**the fab only makes the pcbs but i assembled and fabricate the rest in house! that is what a company does!!!**" What he was making, in his words: "**a full noninvasive bci that ships with firmware preinstalled, the full assembled pcb stack with standoff, in 3d printed enclosure with a strap and lipo battery all assembled. it is literally work out of the box assembled.**"

Updates had to be safe before anything shipped. Every firmware update is signed, so the device accepts only genuine firmware, and an update that fails cannot leave the device unusable.

On September 20 Kris wrote: "**this is final validation for the mass produced production model IntoMind One. i cannot afford to ship defects, not even minor ones.**"

The next day unit one went through its first full acceptance test, the set of checks every unit has to pass. At each of its three sample rates, about 250, 500 and 1,000 per second, it lost no samples. Its noise, the faint electrical hiss every measurement carries, was 0.136 to 0.151 microvolts at 250 samples per second. A signed update sent over Bluetooth arrived and checked out.

Unit one was ready for a model.

## Model Ready

*Part 8*

The student had been waiting on the training machine since August. As unit one came together, Kris Droste brought it into the launch: "**we can also consider including the tiny foundation model in this initial firmware release as something that devs can build on.**"

The AI recommended against putting it on the device at launch, for robustness, and suggested running it on the user's computer instead. Kris's answer, quoted at the start of this story, was that the model "**fits on a chip precisely for the reason of fitting it on a chip.**"

On September 19 the software around the device took the GNU Affero General Public License, a copyleft license that keeps derived work open, with commercial licenses available. The AI had suggested Apache, a license with fewer conditions. Kris: "**huh? i said copy left not apache.**"

The firmware's version of the model has to give the same answers as the training code. For the model the device runs today, Mu 171K, the check was run on a computer on October 4, with the learned numbers stored at 8 bits each exactly as the device holds them. The two agree to a cosine similarity of 1.000000000 over 16 test windows, a score on which 1 is a perfect match, and no number differs by more than 0.0000004.

On September 20, reviewing the firmware's design, the AI proposed taking the model out. Kris: "**you cannot just haphazard propose something like 'remove the ai foundation model'! what are you even thinking? you are drifting.**"

Then the pieces came together. Firmware 1.0.1, on September 24, proved that signed updates worked, and unit one passed its acceptance test five times out of five. Firmware 1.1.0, on September 25, moved the filters that clean the signal onto the device, and the device declares them in the data it sends. The heads, the small add-ons that turn the model's numbers into answers, would be open for anyone to train and load.

On September 25, for the first time, a unit carried the model and ran it, and the firmware reported the model ready.

The next morning, the model needed fourteen seconds per window.

## Four Seconds

*Part 9*

By the morning of September 26, the model on unit one was taking about 14 seconds to work through four seconds of signal. Kris Droste wanted the IntoMind One to run in real time, every window finished before the next arrived, and it was more than three times too slow.

He asked the training machine for two things: first the heads for age and sex, and then "**a distillation ladder to see how small the foundation model can go while still beating or matching psd**". PSD, the power spectral density, is the measurement band power is computed from. A ladder trains a series of ever smaller students the same way and stops at the first one that fails.

Two lines of work ran through the day. On the device, the firmware got faster: 14.13 seconds per pass, one run of the model over one window, then 9.97, then 8.63 by midday. It was still too slow.

On the training machine, an AI agent built the heads and climbed down the ladder at the same time, in a run of five hours and twenty-four minutes. A student of 240,480 parameters passed. One of 123,072 fell short, narrowly, at telling women from men. One of 170,772, trained in between, passed. That made 170,772 the smallest rung that still matched band power. It needed 14.6 million multiply-adds per window, the basic arithmetic steps of a model, against 43.5 million for the model on the device.

That night Kris ruled that it would ship. Nineteen minutes later it went onto unit one over Bluetooth, and after a restart early the next morning, each pass took 3.15 seconds. The device described a window every 4.2 seconds and lost no samples.

It was not free. Tests that followed showed that on every test of its heads, the smaller model did a little worse than the larger one.

On the firmware that units ship with, 1.4.5, the windows run back to back, and a pass takes 3.504 to 3.507 seconds, measured over 12 passes. It fits inside four.

The model was later named Mu 171K.

## Back to Signal

*Part 10*

Mu 171K does more than sum up a window. Along the way it describes the window in pieces. Each electrode's four seconds are cut into slices of a fifth of a second, 100 samples each, and each slice becomes a token, a list of 76 numbers. The device can send those tokens out.

The documentation said that a reconstruction head, an open add-on, would turn a token back into the slice of signal it came from. When that was tested on the device's own tokens, it scored an R² of −0.12. R² measures how much of a signal's variation is recovered: 1 is all of it, 0 is no better than a flat line, and below 0 is worse than that. The head had been trained on the pieces hidden during the teacher's kind of training, not on the tokens the device actually sends. The claim in the documentation, which the AI had written, was false.

Kris Droste ruled that it would be fixed, and the brief for the next run records the ruling: "The open reconstruction head must do what the docs say it does: turn a token the device sends into the slice of signal it came from." His response to the findings was blunt: "**my intuition is that you might be being lazy or drifting and that the correct thing has not yet been built.**"

The rebuilt reconstruction head is a decoder, a map from the model's numbers back to the signal, and it is linear, the simplest kind. It was scored on recordings from studies it never trained on, leaving out the windows with extreme amplitudes, about 4 percent of them. On the rest it recovers an R² of 0.660, and 0.668 on the studies kept aside only for final testing. It does best on slow rhythms and worst on fast ones: 0.87 from 1 to 4 cycles per second, 0.73 in the alpha range from 8 to 13, and 0.12 from 30 to 45.

The windows left out matter. They carry 92 percent of the signal's power, and with them included, the pooled R² falls to 0.058. The typical window, extreme ones included, is still recovered at a median R² of 0.68.

## Worn or Not

*Part 11*

On September 25, Kris Droste made generation a launch requirement: "**generation cannot wait. generation must ship with the product launch.**" Generation means producing a synthetic EEG signal, one that no brain made.

A day later he asked for it on the device itself: "**is there a way to make it so that the reconstruction head can run on the device, enabling a synthetic-stream mode. that would be ideal.**" The AI proposed driving the reconstruction head from a prior in token space, a model of which tokens are likely. Kris checked that he had it right: "**a prior in token space seems like what we have been converging on. it will allow the device to produce synthetic signal endlessly and reliably regardless of whether it is worn or not, right?**" He saw the point of it, "**a clean, reliable synthetic signal generator could be a real useful tool**", and set a condition: "**we should still measure it, since this is somethng that will need to go in the dev docs**".

The first attempt was told apart from real EEG by the encoder itself, the model that turns EEG into tokens, with an AUC of 0.999: almost perfect detection.

The brief for the next run set Kris's standard: the synthetic signal "must produce a signal that the encoder itself cannot tell from real EEG, or come as close as a device-sized generator can".

The generator that shipped is a small model, trained with the encoder in the loop. A linear judge, the same kind of simple readout used everywhere else in this story, scores it at an AUC of 0.552. Kris wanted the measurement reported either way: "**the measurement is a finding.**"

Firmware written on September 27 moved the generator onto the device, and it first ran on unit one early on September 28. With its ADC switched off, the IntoMind One can produce a synthetic signal for as long as it runs, worn or not. Every export of synthetic data is labeled as synthetic, with names such as "ch1_synthetic_uv".

The same day Kris set a rule: "**i think only one ai model should run at a time.**" While the generator runs, the encoder does not. Firmware 1.3.3, on September 28, made it so.

A last rule went back to July's design review and the battery rule that came out of it. On October 2 Kris wrote: "**no functions that requires the user to wear the device runs while plugged in. the generator for purely synthetic signal should still run.**" Firmware 1.4.0, the same day, refuses to stream real EEG on USB power. The synthetic signal still streams.

## Fix Them and Then Launch

*Part 12*

The last week before launch was about trusting the data.

Between September 28 and October 2 the final production board, IM-1.1.7, was settled. Kris Droste's standard for the data it carries: "**dropped packets are not acceptable. period.**" A packet is a small bundle of samples sent over Bluetooth.

On September 29 unit one and the IM-1.0 prototype streamed to one laptop at once, at 250 samples per second each, for 60 minutes and 15 seconds: 903,780 samples from one, 903,762 from the other, and none lost.

Firmware 1.3.7, on October 2, brought the device's clock to within 4 or 5 parts per million, under two hundredths of a second an hour. Kris: "**timing precision is everything.**"

On the morning of October 4, Kris wrote: "**right now i have actually decided to launch the product today.**"

Before launch, firmware 1.4.2 built the age head into the device, selected from the moment it powers on and run whenever predictions are switched on, with the sex head stored beside it. Version 1.4.5 is the firmware units ship with. With the model on, at 1,000 samples per second, a test run delivered 300,264 samples and lost none.

On October 5 Kris wrote: "**fix them and then LAUNCH.**" Two minutes later the five public repositories went live, the places where code is published for anyone to read and use: the software that talks to the device, the developer kit, the Command Center, the open heads and the documentation. Over the next 43 minutes the developer packages were published, and docs.intomind.com went live.

That night unit one was timed on the shipping firmware. Over 12 back-to-back windows, each pass took 3.504 to 3.507 seconds, inside the four.

## Words in this series

- **EEG.** The electrical activity of the brain, picked up by electrodes on the scalp. The voltages are measured in microvolts, millionths of a volt.
- **Electrode, reference.** An electrode is a contact on the scalp. Each electrode's voltage is measured against a reference contact.
- **Window.** Four seconds of signal, the piece the models work on.
- **Corpus.** The collection of public EEG recordings the models learned from.
- **Artifact.** Any part of a recording that is not brain activity, such as a blink or a loose electrode.
- **ADS1299.** The chip in the IntoMind One that measures the electrodes and turns each measurement into a number. It is an ADC, the kind of chip that turns an analog voltage into digital numbers.
- **Sample rate.** How many measurements are taken each second. 500 samples per second is 500 measurements on each electrode every second.
- **nRF52840.** The small processor with a Bluetooth radio that runs the IntoMind One.
- **Firmware.** The software that runs inside a device.
- **Model.** A program that is trained on examples rather than written line by line.
- **Parameter.** One of the numbers a model learns. Mu 171K has 170,772 of them.
- **Training step.** One round of learning, on a batch of examples.
- **Without labels.** Learning from the recordings alone, without being told anything about the people in them.
- **Foundation model.** A model trained on a great deal of data without labels, so that it can later be put to many uses.
- **Teacher, student, distillation.** A small model, the student, is trained to reproduce what a large model, the teacher, says about the same data.
- **Mu 17.8M, Mu 492K, Mu 171K.** The IntoMind Mu models: the teacher, the larger student, and the student that runs on the IntoMind One.
- **Encoder.** A model that turns EEG into numbers. The IntoMind Mu models are encoders.
- **Embedding.** The list of numbers a model produces to describe a window of EEG.
- **Token.** The list of numbers a model produces to describe one short slice of the signal.
- **Decoder.** A map from a model's numbers back to the signal. The open reconstruction head is a decoder.
- **Head.** A small add-on that turns a model's numbers into an answer, such as an estimate of age.
- **Pass.** One run of a model over one window.
- **Multiply-add.** The basic arithmetic step a model takes. Counting them measures how much computing a model needs.
- **Band power.** The classic summary of EEG: how strong each of the brain's rhythms is.
- **PSD.** The power spectral density, the measurement band power is computed from.
- **AUC.** How well a test separates two groups. 0.5 is a coin toss, and 1.0 is perfect.
- **R².** How much of a signal's variation is recovered. 1 is all of it, and 0 is no better than a flat line.
- **Real time.** Finishing each window of EEG before the next one is ready.
- **Synthetic signal.** EEG-like signal produced by a model rather than by a brain.
- **Noise floor.** The level of a measuring chip's own electrical noise, below which it cannot see a signal.
- **Datasheet.** The manufacturer's document that specifies a chip.
- **Short circuit.** An unintended electrical connection.
- **Acceptance test.** The full set of checks a unit has to pass.
- **Over the air.** Sent to the device by Bluetooth, with no cable.
- **Packet.** A small bundle of samples sent over Bluetooth.
- **BCI.** A brain-computer interface.
- **API, SDK.** The API is the set of commands through which programs talk to the device. An SDK is a developer kit built on it.
- **Repository, repo.** A place where code is published and kept.
- **PCB.** A printed circuit board.
- **LiPo.** A lithium-polymer battery.
- **Mains.** Power from the wall.
- **Bring-up.** The first power-on and testing of a new device.

---

*Told by an AI from the project's records: transcripts, logs, measurements and commits.*
