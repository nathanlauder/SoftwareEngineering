# Software Engineering

## Assignment 1 - Hero Villain Matrix
Added a loop to help the agent find the open door in the current state.

## Assignment 2 - Chess AI and Player
#### Chess AI
- Add learning rate of 0.002 to Adam optimizer in each of the models
- Change batch sizing to 32 in model fit
- Increase epochs to 200 in model fitting
- Increase hidden layer nodes to 15 in each model
  - *I would like to increase the hidden layer more, but it would take a really long time for my computer to run it*

The original loss was roughly 0.0681 at the lowest end on the piece model.  Adding a learning rate to the Adam optimizer decreased the loss of all models slightly.  Adding more nodes in the hidden layer dropped that piece loss to 0.0631.  The low end of the alpha model was 0.1141.  Adding more nodes to that model dropped it to 0.1050. The low end of the number model was 0.1094.  Adding more nodes to that model dropped it to 0.1062.

When evaluating the chess game, the machine performs better than the original, but not by a lot.  I think more nodes would help that situation to a certain extent.  There are still poor moves being made in the game, but the opponent punishes those mistakes much quicker.

#### Chess GAN Player
- Use MSE in GAN compilation instead of MAE
- Change alpha to 0.2 in discriminator and encoder of LeakyReLU
- I attempted to add another encoder and decoder, but I couldn't fix the data shaping problems
- resolve new_chess_dictionary by adding a function to get the pieces

Of any of the changes I make, it doesn't seem to be minimizing loss.  However, when comparing my output to the output of the original code, my board is much closer to something that would be real.  The original code had some output where one color had multiple bishops and queens.  Obviously this is not possible.  With my output, the board layout is a possible chess position.

## Assignment 3 - Doom
- Increase batch size
- Increase episodes to 2000
- Train over 10 iterations instead of 5
- Make learning rate 0.001

After these changes, the agent started looking for more health packs.  It still runs into the wall toward the end, but his journey did include looking for more reward.  I would imagine a smaller learning rate with a larger number of training iterations would help, but it would take a very long time to train that agent.

## Assignment 4 - Neural Translation
- Decrease batch size to 32
- change learning rate to 0.02
- monitor accuracy instead of validation loss

I also attempted to increase the total data size to 20,000, but that was taking over an hour to run the entire project.  With a smaller learning rate and batch size, the accuracy of the model would increase significantly, but it did see some improvement in the statistics.  Once again, I attempted to make these changes to find that it was taking an extremely long time to run as well.  With the changes I did make, I was able to bring loss down from 0.5667 to 0.4897. They also provided more reliable predictions in the BLEU scores.
