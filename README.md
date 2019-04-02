# Conversation Initiation Dataset
In our everyday chit-chat, there is a conversation initiator, who proactively casts an initial utterance to start chatting. However, most existing conversation systems cannot play this role. Previous studies on conversation systems assume that the user always initiates conversation, and have placed emphasis on how to respond to the given user's utterance. As a result, existing conversation systems become passive. Namely they continue waiting until being spoken to by the users.
To tackle this problem, we created a large-scale dataset for training and evaluating conversation initiation models through a crowd-sourcing service.
Here, we consider a task setting in which the system initiates a conversation by talking about a news topic. In this setting, the system is provided with a news post to talk about and uses it to generate the initial utterance of the conversation.


## License
[Creative Commons Attribution 4.0 License](https://creativecommons.org/licenses/by/4.0/legalcode)

## Dataset Description

### Input (news contents)
* `src_*.tsv`: are input files used as source sentences for training and testing an encoder-decoder based conversation model. This file contains tweet IDs of @YahooNewsTopics. You should replace each line with an original news post (You can extract the corresponding news post using https://twitter.com/YahooNewsTopics/status/XXXXXXXXX; XXXXXXXXX is tweet ID).
  * You have to remove URLs and first tokens surrounded by "【" and "】" from the tweets.
  * If you have troubles collecting tweets, please contact the [author](akasaki@tkl.iis.u-tokyo.ac.jp).

### Output (summarization and chit-chat)
* `tgt-sep_*.tsv`: are output files used as target sentences for training and testing an encoder-decoder based conversation model. These files can be used for developing **Separate** model (denoted as **Separate(Gen)** or **Separate(Gen+MMI)** in NAACL paper), first column is a summarization part and second is a chit-chat part.
* `tgt-joint_*.tsv`: are output files used as target sentences for training and testing an encoder-decoder based conversation model. These files can be used for developing **Joint** model (denoted as **Joint** in NAACL paper).


Note that all the files must be tokenized using [MeCab ver. 0.996](https://drive.google.com/uc?export=download&id=0B4y35FiV1wh7cENtOXlicTFaRUE) with [ipadic dictionary](https://drive.google.com/uc?export=download&id=0B4y35FiV1wh7MWVlSDBCSXZMTXM). You can easily do tokenization by using `-O` option. 
For installation, [this document](https://github.com/jordwest/mecab-docs-en) might be useful.

## Citation
```
@inproceedings{akasaki2018ci,
  title     = {Conversation Initiation by Diverse News Contents Introduction},
  author    = {Satoshi Akasaki and Nobuhiro Kaji},
  booktitle = {Proceedings of the 2019 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies},
  pages     = {to appear},
  year      = {2019},
}
```



