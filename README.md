# 2024-personal_phishing
These files were used in the CHI'25 paper *It’s a Match - Enhancing the Fit between Users and Phishing Training through Personalisation*.

[Paper](https://doi.org/10.1145/3706598.3713845) - [Pre-registration](https://osf.io/ub5jp) - [Data](https://doi.org/10.3929/ethz-b-000721196)

They contain files that were used for the classification task and the different training variants, excluding the NoPhish videos.

## Overview
This repository contains the code for three elements:
* **The classification task**: Displays a specific email, allowing users to judge whether it is phishing or not.
* **The background task**: Starts a backround task, which allows users to interact with an emulated mailbox, and which occasionally displays banners (banner images not included).
* **The interactive phishing training**: Starts a short interactive training, showing users email examples, prompting a choice, and providing direct feedback.

These files can be flexibily integrated into any tool that allows JavaScript.

### Classification Task
Requires only *email_class.html*. This is primarily a display element that can be combined with a question. However, the email ID to be shown is currently hardcoded on the page, and needs to be manually changed to show different emails.

### Background Task
Requires *email_store_emails.html* to load the used emails and *email_task_redux_notrain.html* to run the background task.

### Interactive Phishing Training
Requires *email_store_training_emails.html* to load the used emails and *email_task_redux_onlytrain.html* to run the training.

## Functionality
These files do not fully resemble the version actually used during the training, for four reasons: 
* The training was run on an Qualtrics instance, which has an unreasonably low character limit per question, which could not easily be adjusted. This prevented us from, e.g., loading all emails in a single question. This is also why there are separate files for loading the emails and for displaying the training.
* To further enable the entire training code to fit within the character limit, the final HTML file was further minified.
* We made some minor adjustments on the live version directly on Qualtrics (e.g., manually adjusting banner timings for different conditions), as the training was developed until data collection started.
* Switching between files and questions was handled by automated Qualtrics logic.

This code is provided as is, and might not fully work as intended outside the Qualtrics environment used during the study.

While an earlier prototype contained the entire training including all conditions in a single file, this approach was abandoned due to time constraints and technical limitations.