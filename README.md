# GNSS_spoofing_detection

## 1. Description of the  Dataset

This project provides the data used in the paper "Small Delay GNSS Forwarding Spoofing Detection in Multipath Environment Based on Convolutional Neural Network." This paper detects small delay forwarding spoofing interference by identifying the shape characteristics of capture correlation peaks during the signal acquisition process of a GNSS receiver. The raw signals are generated and combined through simulations based on the satellite navigation signal model, the forwarding spoofing signal model, and the multipath signal model. The combined signals are then captured using a software receiver to obtain a two-dimensional acquisition matrix, which undergoes processes such as interception and normalization to obtain the detection matrix. Finally, the detection matrix is saved as a two-dimensional grayscale image for model training and testing.

## 2. File Composition

The `Grayscale_Image` directory contains the data used for training and testing the 2D-CNN model. In this dataset, 0 indicates a real signal scenario, and 1 indicates a spoofing signal scenario. The `One-dimensional_Correlation_Peak` directory contains the data used for training and testing the 1D-CNN and Bi-LSTM models.

Dataset/

├── Grayscale_Image/

│   ├── Combination1_9.027MHz_500Hz/

│   │    ├── 0/

│   │    │     ├── num_19_PRN_2_multi1_1.00_delay_0.80_gain_-0.54_multi2_1.00_delay_1.80_gain_0.34.png

│   │    │     └── ...

│   │    └── 1/

│   │    │     ├── num_2388_PRN_1_sGain_1.67_sDelay_1.10_multi1_1.00_delay_1.00_gain_0.57_multi2_1.00_delay_0.40_gain_0.21.png

│   │    │     └── ...

│   ├── Combination2_16.368MHz_500Hz/

│   │    ├── 0/

│   │    │     └── ...

│   │    └── 1/

│   │          └── ...

│   ├── Combination2_16.368MHz_500Hz/

│   │    ├── 0/

│   │    │     └── ...

│   │    └── 1/

│   │          └── ...

│   └── Combination2_16.368MHz_500Hz//

│         ├── 0/

│         │     └── ...

│         └── 1/

│                └── ...

└── One-dimensional_Correlation_Peak/

├── Combination1_9.027MHz_500Hz.csv
    
├── Combination2_16.368MHz_500Hz.csv
    
└── Combination3_25MHz_500Hz.csv

## 3. File Naming Format

`CombinationX_YMHz_ZHz`

$X$ represents the combination name, $Y$ represents the sampling frequency, and $Z$ represents the frequency search step size.

The genuine signal scenarios：`num_a_PRN_b_multi1_c_delay_d_gain_e_multi2_f_delay_g_gain_h.png`

$a$ represents the sequence of data production, $b$ represents the satellite $PRN$ number, $c$ represents the identifier of the first multipath signal, where $1$ indicates its presence and $0$ indicates its absence, $d$ represents the delay of the first multipath signal, $e$ represents the attenuation factor of the first multipath signal amplitude, $f$, $g$, and $h$ represent the information of the second multipath signal, with meanings equivalent to those of the first multipath signal information.

The spoofing signal scenarios：`num_a_PRN_b_sGain_c_sDelay_d_multi1_e_delay_f_gain_g_multi2_h_delay_i_gain_g.png`

Compared with the data of the real signal scenario, the spoofed signal has two more parameters $c$, $d$, which represent the gain and delay of the spoofed signal, respectively.
