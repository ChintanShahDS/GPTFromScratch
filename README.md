# GPTFromScratch
- Model deployed on https://huggingface.co/spaces/Chintan-Shah/ScratchGPTChar
- 2 different version done (Uploaded the 2 notebooks)

## Trained an own GPT from scratch
- Used a normal GPT architecture with decoder only for prediction next token
- Trained for story dataset having small stories
- Tokenized on characters and not works or part words - This helped in ensuring able to train the model with limited vocab on small GPU
- Also tried training with OneCycleLR Scheduler but did not see any significant difference due to the size of the model as well as vocab probably
- Able to get decent results though not as good as other LLMs but then this is char based vocabulary
- Able to reduce the eval loss to almost 1.1370 and train loss to 1.1208
- Also trained for Shakespeare data from https://github.com/karpathy/nanoGPT/tree/master/data/shakespeare but deployed the Story one on huggingface

## Configurations used
- Optimizer: AdamW
- Scheduler: OneCycleLR (learning_rate = 1e-2)
- Loss: CrossEntropyLoss
- Dataset: roneneldan/TinyStories (Some part)
- AMP with Grad Scaler used
- 0.211922 M parameters

## Observations
- Stored stoi and itos also in files for hugging face spaces
- Usage of OneCycleLR and AMP does not help much in time or loss reduction
- Smaller dataset it seems it is better able to give the outcomes
- More iterations is improving the performance (Did max of 10000 iterations)

## Things want to do
- Train on Panchtantra stories and test

## Logs
- Output for 10000 iterams OneCycleLR and AMP
step 0: train loss 4.4946, val loss 4.4933, lr 0.00000000
step 1000: train loss 1.7181, val loss 1.7251, lr 0.00340110
step 2000: train loss 1.5288, val loss 1.5157, lr 0.00670220
step 3000: train loss 1.4592, val loss 1.4642, lr 0.00999857
step 4000: train loss 1.3737, val loss 1.3779, lr 0.00857014
step 5000: train loss 1.3137, val loss 1.3177, lr 0.00714171
step 6000: train loss 1.2647, val loss 1.2751, lr 0.00571329
step 7000: train loss 1.2262, val loss 1.2401, lr 0.00428486
step 8000: train loss 1.1763, val loss 1.2013, lr 0.00285643
step 9000: train loss 1.1506, val loss 1.1553, lr 0.00142943
step 9999: train loss 1.1208, val loss 1.1370, lr 0.00000243

- Output for 5000 iterations regular
step 0: train loss 4.6078, val loss 4.6064
step 100: train loss 2.4858, val loss 2.4901
step 200: train loss 2.3518, val loss 2.3439
step 300: train loss 2.2287, val loss 2.2211
step 400: train loss 2.1138, val loss 2.1234
step 500: train loss 2.0444, val loss 2.0483
step 600: train loss 1.9626, val loss 1.9692
step 700: train loss 1.8922, val loss 1.9009
step 800: train loss 1.8447, val loss 1.8475
step 900: train loss 1.7947, val loss 1.8074
step 1000: train loss 1.7376, val loss 1.7363
step 1100: train loss 1.7110, val loss 1.7162
step 1200: train loss 1.6746, val loss 1.6773
step 1300: train loss 1.6417, val loss 1.6564
step 1400: train loss 1.6283, val loss 1.6359
step 1500: train loss 1.5994, val loss 1.6126
step 1600: train loss 1.5733, val loss 1.5862
step 1700: train loss 1.5629, val loss 1.5719
step 1800: train loss 1.5490, val loss 1.5586
step 1900: train loss 1.5296, val loss 1.5426
step 2000: train loss 1.5089, val loss 1.5316
step 2100: train loss 1.5284, val loss 1.5236
step 2200: train loss 1.4958, val loss 1.4977
step 2300: train loss 1.4859, val loss 1.4926
step 2400: train loss 1.4783, val loss 1.4913
step 2500: train loss 1.4659, val loss 1.4761
step 2600: train loss 1.4549, val loss 1.4777
step 2700: train loss 1.4494, val loss 1.4542
step 2800: train loss 1.4499, val loss 1.4517
step 2900: train loss 1.4319, val loss 1.4341
step 3000: train loss 1.4235, val loss 1.4316
step 3100: train loss 1.4207, val loss 1.4210
step 3200: train loss 1.4141, val loss 1.4263
step 3300: train loss 1.4003, val loss 1.4057
step 3400: train loss 1.4006, val loss 1.3996
step 3500: train loss 1.3874, val loss 1.4140
step 3600: train loss 1.3840, val loss 1.3839
step 3700: train loss 1.3917, val loss 1.3934
step 3800: train loss 1.3633, val loss 1.3852
step 3900: train loss 1.3689, val loss 1.3877
step 4000: train loss 1.3774, val loss 1.3834
step 4100: train loss 1.3662, val loss 1.3826
step 4200: train loss 1.3526, val loss 1.3734
step 4300: train loss 1.3670, val loss 1.3710
step 4400: train loss 1.3465, val loss 1.3580
step 4500: train loss 1.3356, val loss 1.3609
step 4600: train loss 1.3491, val loss 1.3604
step 4700: train loss 1.3463, val loss 1.3488
step 4800: train loss 1.3345, val loss 1.3471
step 4900: train loss 1.3223, val loss 1.3443
step 4999: train loss 1.3293, val loss 1.3342

## Output
- 10000 iterations with OneCycleLR and AMP output: learn. She hugs them and have a bike. So he made that he couldn't boy. He you feel get prace?" Sara's friend replied and hop as her sad.  The next day, they feel safe behind. When she saw a blue guard and speed to the race to the morous and kept sometimes the new and play with her friends. The car was happy. But he wished all they knew they would use it in the ground. "It's. So, book they can sheep are freree and plants," says. "It's lots of a bear!" Sara said.Tom said.Lily his to be pot zirring to towa.But the creator was three yeared. "Thank you, there was a bite?" Mom said.  "What was a very year!" Her milk asked the box out of bounny and flew awepended. Lily wanted to tell and play with his powith. She smiled on the dog and Today. Tom again the sun they wanted to gift school every day, the bad trusted and saw the sunshine.  The gunners smiled and does to give the burth and people that day, Lily felt proud children. She felt the same warrows on a face nower was it too!", he said.  Jack and Ben showed the truck bigger friends. They made it best off his friends and just wanted to be fun took them. The feresh and always touch.   When Lily wold to play with toy the toys. He was walking to leap out into the rosfies to go after fighter. He benched it for lots of would quickly.  They are sure the pelloctaid in the swing. Come to set burner to coat. So he went to play outside. They hair cooke some with pit, it. So, the colorful batheadowled something in magic his swam and dad was too be bearning for right, it made better plants and jellly the top an. The dog sweped and said, "I give you are nest naughty." Sirry twinked around and they found to the kite truck reamed the wall to it's scared ir to play outside, and he called a happy and the little girl who had a snaked.  Her friend Lily made sure, Mom and stoving. When it is bucked and safe. Lily sad and bright it and said, "Can I hey, but it is down, here, she wanted to eat all and ugles. He loved to play with the water."
- 5000 iterations with normal training output: i, Petion. Walked to one he his mantus of a move helpper a ground sorry cel and day. One day, You he had say. Let's careful. She loved it was for and saw a pictures noise. He lost!  She says what the spry outside and for a smile and was a little. Sara and got bools friends and car bricks.Lily are repts hers at away. You are did and selising to bettere.   Jurn th all wrick.   On make upone and she was a little girl who knowed. Then is everyones the hugh. It is some was sowing, "Momma, you, you and Tommy. They need little girl named But and shook new and. Lily getted a look, "Whitter, stair you! Sha had, "We hance all lots of shandy, Lily saw a knew storing read. It some chele friends his now. I liked to the straphe. She was happy. They were has mued. He was Ben, sto they puall shouts waal again.  Tim was contiesly she asked She was climed to say and a pect and to highs pemhas always statchile.  Thanked her chamber and grass.  The twered tume. The Sall scarage race saw a gag. He sho loned to her, Mia and Tom and great it bebring to swerk beat give it returs and it were need aroundror." The fish said, "Thank. Sam says "You are ran you cana, "Now, Lily, and Timmy. He wanted to shak ew him stopped ut when he wantered. This go was strapplied.  Fided a friends noised had a parriend coinous on frgers, "Now, when I wers cat Jat? Lily says, "What poonife you flowers aniones, and Anna had something quickly. She wanted to noise hopped foll sh his nex again inyth their bun. "Okay, Lily said You are and eTimmy was a the helppiled. She was very bupnice. She need ge a ball. She loved to everyone withere the bell and freetimes inside. It helped when she neader, Mummy and them. Mom and Dank hohy hand hear nigh. She said "Nou this ck back. They said "They happy are you and both happy and the shook. They went her momm! She was had he was so happy to sucgies a green.   Lily was very pretty.  "I heard, you, Mom!" The loted special new shaked a spic in it. He saw his not fun worrite. The
