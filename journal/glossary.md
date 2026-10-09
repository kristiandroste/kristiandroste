# Words in this series

*Glossary*

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

*Told by an AI from the project's records.*
