
# Additional Leaderboards

The leaderboard on the [main page](https://github.com/DeepPavlov/convai/blob/master/README.md) is the results on the hidden test set for the ConvAI2 competition, which will serve as the main results dictating which models graduate to the Mechanical Turk human evaluation round on September 30th.
On this page will we add additional scores of interest: currently, results on the validation set which are good for calibration, and are the actual numbers you would see if you run the evaluation scripts locally (as you do not have access to the hidden test set for the main leaderboard; those are run by us when you submit your model).
We will add the revised persona leaderboard here soon too.

## ConvAI2 Validation Set Leaderboard


| Model                | Creator  | PPL           | Hits@1  |   F1   |
| -------------        | ---      | :------------- | :-----  |  :----- |
|                      |&#x1F917; (Hugging Face) | 23.05&#x1F34E;   | 74.3&#x1F34E;   | 17.85&#x1F34E; |
|                      | High Five | - | 66.2   | - |
|                     | Pinta            | -	     | 51.4   | 17.25	|  
|                     | NEUROBOTICS      | 39.7	   |-       | 16.82	| 
|                     | Sonic            | 38.87	 |-       | 16.88	|  
|                     | Tensorborne      | 44.64      |  12.1       |  16.13|
|                     | loopAI           | -       |  29.7 |  -  |
|                     | Lost in Conversation| 62.83	 | -    | 15.91 | 
|                     | flooders         | -     	 |-       | 15.96	| 
|  [Seq2Seq + Attention](https://github.com/facebookresearch/ParlAI/tree/master/projects/convai2/baselines/seq2seq)  | ParlAI team          | 36.5        | 18.3       | 16.82 |
|  Language Model       | ParlAI team          | 51.1       | -       |  15.31|
|  [KV Profile Memory](https://github.com/facebookresearch/ParlAI/tree/master/projects/convai2/baselines/kvmemnn)    | ParlAI team          | -             | 55.1  |  11.72 |

&#x1F34E; denotes the current best performing model for each metric on the validation set.

Models by ParlAI team are baselines, and not entries into the competition; code is included for those models.
