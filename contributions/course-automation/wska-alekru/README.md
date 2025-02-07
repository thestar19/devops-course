<<<<<<< HEAD
# Course automation: Post hemingway editor score, readability and feedback (Proposal #1041)
=======
# Course automation: Post hemingway editor score, readability and feedback
>>>>>>> upstream/2021

## Members

William Skagerström (wska@kth.se) (@wska)
Alexander Kruger (alekru@kth.se) (@TheStar19)
## Introduction

<<<<<<< HEAD
The code is hosted here: https://github.com/wska/hemingwayAutoFeedback

This contribution takes the form of a bot that is capable of providing feedback on an essay submission by utilizing the online-hosted hemingway editor (https://hemingwayapp.com/). The hemingway editor will provide some general information about the text that was published, including:
=======
This contribution takes the form of a bot which is capable of providing feedback on an essay submission by utilizing the online-hosted hemingway editor (https://hemingwayapp.com/). The hemingway editor will provide some general information about the text that was published, including:
>>>>>>> upstream/2021
* A approximative grade of the readability of the paper (generated by a heuristic)
* Word count
* Reading time
* Quantity of adverbs utilized
* Uses of a passive voice
<<<<<<< HEAD
* Phrases that could be rewritten in a simpler manner
=======
* Phrases which could be rewritten in a simpler manner
>>>>>>> upstream/2021
* Number of difficult to read sentences
* Number of VERY difficult to read sentences

## General functionality
The program performs the following steps when execution initiates:
1. Scans the pull requests available on the designated repo and looks for comments including the "!hemingway" tag.
2. If the pull request contains a pdf file, it will download it and convert it into a raw text file using pdf2txt.py library (https://pypi.org/project/pdf2text/). 
3. The text will then pass into a hemingway function, which utilizes selenium and google chrome to open a web browser and input the raw text (https://selenium-python.readthedocs.io/).
4. It will then fetch the relevant feedback provided by the hemingway editor and create a short summary.
5. This is then returned and posted as a comment to the original pull request using a dedicated bot-account. Git interactions are done using pygithub (https://pygithub.readthedocs.io/en/latest/index.html).

<<<<<<< HEAD
An example of a PR submission which is scanned and provided with the hemingway scores can be viewed under active pull requests.

## How to use
The bot will trigger its search upon seeing a pull request by default. In order to obtain hemingway feedback, one needs to either include a comment on the pull request which includes "!hemingway" (with a exclamation mark), or include the phrase in the body of the pull request.

The search can also be manually started by going into Github Actions and scheduling the "hemingway'' job. This might be necessary if one makes a comment after a pull request and wants to obtain feedback.

### Configuration
To configure the bot, place the entire repo in one folder. Depending on your repo, the path to pdf2txt.py may be different, please adjust by noticing from the debug text where it attempts to run the pdf2txt.py file and adjust the path on line 120 accordingly.

The heminwayfeedback.yml file needs to be in root/.github.

To start the bot, run python3 main.py TOKENID REPO_ID REPO_NAME. 
This may need to be adjusted in the hemingwayfeedback.yml depending on your setup where line 50 needs to be run: python ./main.py $SUPER_SECRET REPO_ID REPO_NAME or set in main.py manually.

One way to obtain the REPO_ID is to inspect a repository through a modern web browser and paste the following command into the console:

> $("meta[name=octolytics-dimension-repository_id]").getAttribute('content')


This also makes it possible to target more than one repo at once. The $SUPER_SECRET can be a access token or the GITHUB_TOKEN which is generated for GitHub actions. See this for more information: https://docs.github.com/en/actions/reference/authentication-in-a-workflow


## Submission details

For this task, we aimed at fulfilling yes for all points except for the point about praise from other students, since this is subjective and unreliable at best. Note that we squashed the commit history into one commit to keeping the history of the main repo clean. The overall work distribution was about equal. 


|                                             | Reasoning | Remarkable |
|-------------------------------------------- |----|-------------|
|The work is done before April 6, 2021 (in order to be useful for the course) | PR done 5th of April | - |
|The automation task produces a PR status or issue / PR comment | Produces a comment on a PR. | - |
|The automation task is reusable | As a github action, it may be applied to any other repository which hemingway feedback may be useful | “In other courses than this one”: If the course is based around github like this one, then yes. |
|The task runs on a standard platform | Yes, runs on Github Actions| - |
|The code for the task is available | Yes, repo: https://github.com/wska/hemingwayAutoFeedback | “Well documented repo”: While subjective, we would say that the repo is well documented |



=======
## How to use
The bot will trigger its search upon seeing a pull request conducted to the ./contributions/essay path. In order to obtain hemingway feedback, one needs to either include a comment on the pull request which includes "!hemingway" (with a exclamation mark), or include the phrase in the body of the pull request.

The search can also be manually started by going into Github Actions and scheduling the "hemingway'' job. This might be necessary if one makes a comment after a pull request and wants to obtain feedback.
>>>>>>> upstream/2021
