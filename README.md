# predict_rating
## about this project
This project is to examine non_human_analytics against company liablities, using Osiris(https://osiris-r1-bvdinfo-com.waseda.idm.oclc.org/version-20230215-1-0/home.serv?product=OsirisNeo& ),an database site about company informations, and predict Mody's longterm rating by machine learnning. In this project I used 2 type of machinelearning, NN and Light GBM, and latter realize 0.8 mae on this scale.  
  
### sclale I used in this project
| Mody's rating | scale |
| --------------- | -------- |
| Aaa             | 21       |
| Aa1             | 20       |
| Aa2             | 19       |
| Aa3             | 18       |
| A1              | 17       |
| A2              | 16       |
| A3              | 15       |
| Baa1            | 14       |
| Baa2            | 13       |
| Baa3            | 12       |
| Ba1             | 11       |
| Ba2             | 10       |
| Ba3             | 9        |
| B1              | 8        |
| B2              | 7        |
| B3              | 6        |
| Caa1            | 5        |
| Caa2            | 4        |
| Caa3            | 3        |
| Ca              | 2        |
| C               | 1        |
| WR              | 0        |
  
 if having plus or minus, I add or remove 0.25.
   
 I jugded this program is useful enough, and publish likethis.
 Adding it, I published this project as web app"corp_rater". Unfortunately my buget problem does not allow me to deploy this project, you can realize it by cloning that repository.
 
 ## before you use.
- This projcet fataly lack the source of data. Especially low rating, and very high rating can not be predicted by this model.
- I don't take resoponsibility for loss by using this model.
- If my uploading data is against your IP, Please notice me. Rapidly I will remove that data.
  
 - if you use this model, download data from Osiris using list 3 and predict by for predict by lgb with changing file name. Make sure you installed required files.

## the process I make model
  I downloaded 1000 data from Osiris DB by list3, and teching data of Mody's rating, and after preform, scaled and reduce dimention for 100. After this, I train my model by these paramaters, using closs-balidation.
  
  | paramaters       | index          |
| --------------- | ----------- |
| objective       | regression  |
| metric          | mae         |
| num_leaves      | 128         |
| learning_rate   | 0.02        |
| feature_fraction| 0.9         |
| bagging_fraction| 0.8         |
| bagging_freq    | 5           |
| verbose         | -1          |
| random_state    | 1236        |
