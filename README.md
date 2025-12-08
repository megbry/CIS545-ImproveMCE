# Improve MCE and Defend Against Two Attacks

### CIS 545 Fall 2025 Final Project

## Project Overview
Machine learning models are susceptible to membership inference attacks, in which an attacker tries to identify whether data was included in the model training material. 
MIAShield, an ensemble machine learning classifier using exclusion oracles to defend training data, provides a model confidence based exclusion (MCE) method that removes the most confident model from the final response. 
This project evaluates three alternative exclusion mechanisms: confidence deviation prediction (CDE), historical calibration error weighted prediction (HCE), and hybrid KL divergence prediction (KLD), against the MCE implementation to compare the susceptibility of each potential improvement against confidence and shadow model attacks. 
After evaluation, none of the methods provided significant additional protection over the base MCE implementation when considering attack AUC and advantage, in part due to the strong performance of the base MCE. 

## Project Dependencies

The  models are stable using the following versions:
```txt
numpy==2.3.3
scikit-learn==1.7.2
scipy==1.16.3
torch==2.5.1+cu121
torchaudio==2.5.1+cu121
torchvision==0.20.1+cu121
```

## Project Files

### Initial Setup Files:

These are files related to training the base models and setting up the initial exclusion oracle, MCE.  

Ensemble model training code: https://github.com/megbry/CIS545-ImproveMCE/blob/main/Setup_and_Model_Extraction/The_Setup.ipynb

Model exclusion oracle setup: https://github.com/megbry/CIS545-ImproveMCE/blob/main/Setup_and_Model_Extraction/The_Setup_with_MCE.ipynb

### Improved MCE Files:

These files are related to the proposed changes we are evaluating for effectiveness.

Proposed exclusion oracles (CDE, HCE, and KLD) setup: https://github.com/megbry/CIS545-ImproveMCE/blob/main/Setup_and_Model_Extraction/The_Setup_with_MCE.ipynb

### Attack Files:

These files are related to the two attacks we tested the exclusion implementations against. 
We evaluated the performance of confidence based and shadow model attacks against MCE, CDE, HCE, and KLD, to evaluate which implementation is the most effective. 

#### Confidence Based

Attack against the base MCE: https://github.com/megbry/CIS545-ImproveMCE/blob/main/Confidence_Based_Model_Base_MCE.ipynb

Attack against the proposed exclusion oracles: https://github.com/megbry/CIS545-ImproveMCE/blob/main/Confidence_Based_Model_Modified_MCE.ipynb

#### Shadow Model Based

Attack against the base MCE: https://github.com/megbry/CIS545-ImproveMCE/blob/main/shadow_model_attack_base_mce.ipynb

Attack against the proposed exclusion oracles: https://github.com/megbry/CIS545-ImproveMCE/blob/main/shadow_model_attack_improved_MCE.ipynb

Due to upload size restrictions, the trained model files are only available under megbry-model-branch. 
This branch utilizes Git LFS, which was necessary due to the file size, and left separate to avoid impacting access time for non-model code. These models are:
- f1.pth: https://github.com/megbry/CIS545-ImproveMCE/blob/megbry-model-branch/f1.pth
- f2.pth: https://github.com/megbry/CIS545-ImproveMCE/blob/megbry-model-branch/f2.pth
- f3.pth: https://github.com/megbry/CIS545-ImproveMCE/blob/megbry-model-branch/f3.pth
- f4.pth: https://github.com/megbry/CIS545-ImproveMCE/blob/megbry-model-branch/f4.pth
- f5.pth: https://github.com/megbry/CIS545-ImproveMCE/blob/megbry-model-branch/f5.pth
- shadow_model.pth: https://github.com/megbry/CIS545-ImproveMCE/blob/megbry-model-branch/shadow_model.pth
