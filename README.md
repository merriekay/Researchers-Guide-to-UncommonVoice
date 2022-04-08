# Researcher's Guide to the UncommonVoice Dataset

This guide will take you through the basic steps of getting UncommonVoice loaded and ready to work with.

## How to get the data:
To get access to the dataset, start by emailing meredith.moore@drake.edu with the suject `UncommonVoice Download`. There will be an automatic reply with a link to download the dataset as well as instructions as to how to cite the datset in your work. The zip file is 1.63 GB and includes 3693 speech samples from individuals with and without voice disorders.

## How to cite the data:
BibTex:
```
@article{moore2020uncommonvoice,
  title={UncommonVoice: A Crowdsourced Dataset of Dysphonic Speech},
  author={Moore, Meredith and Papreja, Piyush and Saxon, Michael and Berisha, Visar and Panchanathan, Sethuraman},
  journal={Proc. Interspeech 2020},
  pages={2532--2536},
  year={2020}
}
```
Other formats can be [found here](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C16&q=UncommonVoice%3A+A+Crowdsourced+Dataset+of+Dysphonic+Speech&btnG=#d=gs_cit&u=%2Fscholar%3Fq%3Dinfo%3AwzEJyLPfAG0J%3Ascholar.google.com%2F%26output%3Dcite%26scirp%3D0%26hl%3Den)

## Want more info?
If you're curious about the details of UncommonVoice, you have a few options:
- Read the [Interspeech 2020 paper here](https://img1.wsimg.com/blobby/go/bb8819fe-ceab-4aab-9326-de58f46295cf/downloads/UncommonVoice_IS2020.pdf?ver=1604346789008). 
- Check out my [personal website](https://merriekay.com/uncommonvoice) which basically recaps all of these details.
- Watch the [Interspeech 2020 highlight video](https://youtu.be/QwXwfGbWAH4).
- Or watch the [15-minute Interspeech presentation](https://youtu.be/lBEYCujz2L4).

## Licensing:
UncommonVoice is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/).

# Some Tips/tricks:

## Prompts:
Subjects were asked to complete four sections of data collection: 

1. **Task 1**: Non-words (sustained corner vowels, and DDK rate)

2. **Task 2**: Read Speech: Randomly selected TIMIT sentences and the sentences required to complete the CAPE-V intelligibility assessment

3. **Task 3**: Image Descriptions: Spontaneous speech to describe images from the MSCOCO dataset.

4. **Task 4**: Non-words (round 2 to measure any change in voice over data collection process). 

These prompts can be found in the `prompt` folder. They are split into T1-T4 corresponding to the above tasks. 


## How to decode the filename. 
Filename example: **FD04\_T2\_si1997\_31.wav**

\<**unique ID**\>\_\<**task number**\>_\<**promptID**\>\_\<**number of days post Botox treatment**\>.wav

Let's go character by character:
- **First character** is either **F** or **M** and corresponds to the sex of the participant. F: female, M: male. 
- **Second character** is either **D** or **C** and corresponds to whether or not the speaker has a voice disorder. D: disorder C: Control (no disorder).
- Then comes a number. The combination of the first section of the filename allows us to uniquely identify each participant.
- After the first underscore comes the Task number. For a description of what the task number means, see above.
- After the second underscore comes the prompt. This is what was presented to the individual.For more information on the prompts, see above.
    - Note that for non-words, the prompt does not directly correspond to what the participant said. 
    - For example, the prompt may have been `Please hold /a/ as in 'pot' for 5 seconds` but the speaker did not just read the prompt, they completed the task that it asked.
- Last, but certaintly not least, we have another number. This number corresponds with the number of days since the speaker's last Botox Injection. Botox is the most common treatment for Spasmodic Dysphonia and the speaker's voice may be more or less clear based on when they recieved their last treatment. If this is **NA** then it means that they do not receive Botox treatment.

Filename example: **FD04\_T2\_si1997\_31.wav**

So for the example given above, we know the speech sample:
- came from a female (**F**) with a voice disorder (**D**) and is saying what is found in `si1997.txt`. We also know that it is 31 days since she had a Botox injection.

>If you do not want to decode the files yourself, a key with this information for each file has been included as at [UncommonVoice_file_descriptions.csv](https://github.com/merriekay/Researchers-Guide-to-UncommonVoice/blob/main/UncommonVoice_file_descriptions%20(1).csv)
>
>It has the columns: \<filename,	sex,	disorder,	prompt,	days_since_btx\>

## Survey Results:
As the paper describes, part of the data collection process was asking each speaker a series of questions. While the answers to these questions are not included in the data that is downloaded from the link, I've inlcuded them here as `uncommonvoice_user_data.csv`.

Here is a Table from the paper showing the questions that were asked in the survey: 

![image](https://user-images.githubusercontent.com/5067730/122959440-adaf8780-d348-11eb-89bb-6033a550cf62.png)

## Things to come:
- [ ] A tutorial on getting started with UncommonVoice
- [ ] A notebook that completes common feature extraction techniques (MFCCs, Melspectrograms,...)
- [ ] A calculation of the vowel-space area for each participant before collection and after collection.
- [ ] A basic model that classifies whether or not an individual has a voice disorder using UncommonVoice


