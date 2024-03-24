# HMS - Harmful Brain Activity Classification

This repository contains code for classifying harmful brain activity using electroencephalography (EEG) signals recorded from critically ill hospital patients. This is the submission for Harvard Medical School's Human Brain Activity Classification competition hosted on Kaggle. 

The EEG segments in the dataset have been annotated by experts, resulting in six patterns of interest: seizure, generalized periodic discharges (GPD), lateralized periodic discharges (LPD), lateralized rhythmic delta activity (LRDA), generalized rhythmic delta activity (GRDA), or "other". The dataset includes patterns and edge cases with varying levels of expert agreement.

The code includes signal processing, feature extraction, data preparation, training of a machine learning classifier, and a sanity check. The goal is to improve the efficiency and accuracy of EEG pattern classification, benefiting neurocritical care, epilepsy management, and drug development.

A bandpass filter was used to isolate the frequencies present in an EEG recording, which lie between 0.1 Hz and 50 Hz. Furthermore, a notch filter was used to remove powerline noise. 

##Statistics used as a proxy for the features of the signal:

1. Mean: Central tendency of the signal, this may be higher in seizures and GPD due to higher overall activity, whereas thet might be slightly lower in GRDA and LRDA due to the presence of slow delta activity. Might also reflect asymmetry in LPD and LRDA.
2. Standard deviation: Variability of the signal around the mean: this may be higher in seizures to due drastic changes in amplitude, as well as in LRDA, LPD and GPD.
3. Peak-to-peak amplitude: difference between the highest and lowest points in the data. Likely to be higher in seizures due to more drastic changes in amplitude.
4. Variation: Measure of spread, higher in seizures due to more drastic and frequent changes, as well as in GPD, LRDA and LPD.
The minimum and maximum values of the signal: assessment of amplitude.
5. Square root of the signal
6. Skew: Asymmetry of the distribution, positive in seizures due to asymmetry compared to baseline activity, but also seen in LRDA and LPD as these are lateralised.
7. Kurtosis: Peakedness/flatness of the signal, may be higher in seizure due to more peaks.

These features were then used for model training. An 81.4% prediction accuracy was achieved by the trained model.
