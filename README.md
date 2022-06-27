# PokerPython
POKER GAME with Python

How to make a Python program to determine the winner given two set of cards per the following:   In a card game poker a hand consist of five cards that are ranked from lowest to highest in the following order:

1.	high card: highest card value
2.	one pair: two cards of the same value
3.	two pairs: two different pairs
4.	three of a kind: three cards of same value
5.	straight: all cards consecutive value 6: flush: all cards of same suit 7: full house: three of a kind(same value) and a pair.
6.	four of a kind: four cards of the same value.
7.	straight flush: all cards consecutive value same suit.
8.	royal flash: ten, jack, queen, king, ace same suit.


The cards are value: 2,3,4,5,6,7,8,9,10,Jack,Queen,King,Ace.
Cards are suited as : (S)Spade, (H)Hearts, (D)diamonds, (C)clubs.
The games have a value depending on:
Hand = {"nothing":1, "onePair":2, "twoPairs":3,"threeKind": 4, "Straight":5,
#"Flush":6,"FullHouse":7,"FourKind":8,"StraightFlush":9,"RoyalFlush":10}, being the highest “RoyalFlush’ with 10, and the lowest “nothing” with 1.

If players have the same ranked hand, the rank made up of the highest value wins, example a pair of eights beats a pair of fives.
But if two ranks tie, for example both have a pair of queens, then highest card in each hand are compared. If the highest card tie, then the next highest card are compared, an so on.

Inputs and outputs

Inputs:

Two arrays of five elements with a name of hand, each element represents a card which  is a string of two characters, a number and a suit.  Example: hand1 = ['TC','JC','QC','KC','AC'] and hand2 = ['3C','4C','5C','6C','7C'].  The first element of hand1 is “TC’ which represent the card with number 10 and suit ‘clubs’. One important condition of the array inputs is that they have to be sorted in ascending order.
Output:

There are various games(expressed in a dictionary):

Hand = {"nothing":1, "onePair":2, "twoPairs":3,"threeKind": 4, "Straight":5,
#"Flush":6,"FullHouse":7,"FourKind":8,"StraightFlush":9,"RoyalFlush":10}

The output is a number 1 or number 2, which represents which hand is the winner  out of the two hands. In the example above (hand1 = ['TC','JC','QC','KC','AC'] and hand2 = ['3C','4C','5C','6C','7C']) the winner is hand1.  The hand1 is a “royal flash”,  it has same suit on all cards and consecutive  numbers: ten, jack, queen, king and ace.  The hand2 is a “StraightFlush”, it has all cards with consecutive values staring in ‘3’ and ending in 7 with suit “C”(clubs) with all cards.
“RoyalFlush” has value 10 and “StraightFlush” has value 9, and “RoyalFlush’ has bigger number and wins. The winner is hand1 or just “1”.
Let’s see who wins between one game with   player 1: full house(three of a kind and a pair) and player 2 with game “fourofKind”(four cards of the same value).  The hands are:                          
hand1 = ['3C','3D','3S','2D','2S']
hand2 = ['4C','4D','4S','4H','JH']
Hand1 is “full house”(three of a kind and a pair)  which is valued  7 and Hand2 is “fourofKind”  which is  valued 8.  The winner es Hand2 with a value of 8.
Let’s see another play, player one has  two pairs(2 T’s and 2 K’s) and player two one pair(2 5’s):                                  
hand1 = ['TC','TH','KC','KD','AC']
hand2 = ['3C','5D','5C','8S','9H']
Game “Two Pairs” has a value of “3” and game “onePair” has a value of “2”.  The winner is the higher, which es “	twoPairs” with value of “3”, which is hand1. The winner is 1.
Now, let’s consider having player 1 with game “straight’(all cards consecutive value from 3 to 7) and  second player with the same game “straight’(all cards consecutive value from 5 to 9). hand1 = ['3C','4H','5D','6S','7C']
hand2 = ['5C','6D','7C','8S','9H']
Since they have the same game, they have a value of game “straight’(all cards consecutive value) which is 5.  Now, who wins?.  For that, it has to be considered the last number of the hand, the higher value corresponds to the winner.  The last number to hand1 is “7” and for hand2 is “9”. So, hand2 is the winner.
Now, there are two possibilities when the two hands have the same game.  The first is when the same game has different numbers.  What happened when there are two hands with both consecutive values with same suit?.   Which wins?. Here, the bigger last number wins.  For example, , hand1 = ['3C', '4H', '5D', '6S', '7C'] and hand2= ['5C', '6D', '7C', '8S', '9H'], the winner is 2 because it has the last biggest number of both, number 9.
If there are two cards that  have the same play is when both have the same exact game. Which wins?.  For example, hand1 has one pair of 3’s  with other cards 4,7,9 and hand2 has one pair of 2’s with other cards J,K,A.  Hand1 = [3C,3D,4H,7S,9D]  and hand2 = [2S,2C,JD,KH,AS].  The hand that wins is the one that has the the biggest number of pairs. In this case, hand1 has the biggest pair with number “3”. The winner is 1.
The other possibility  when the two hands have the same play is when both have the same exact game. Which wins?.  For example, hand1 has one pair of 2’s  with other cards 4,7,9 and hand2 has one pair of 2’s with other cards J,K,A.  Hand1 = [2C,2D,4H,7S,9D]  and hand2 = [2S,2C,JD,KH,AS].  The hand that wins is the one that has the the biggest number on the right. In this case, hand2 has the biggest with is “A”. The winner is 2.

Finally, if two hands only have cards with no pairs, or other higher games, the one that wins is the one that has the highest value on the last right card of the hand. Example: 
hand1 = ['2C','4D','6H','8S','AD']
hand2 = ['2S','3C','9D','JH','KH']
 player 1: cards with just values 2,4,6,8,A , other pair 2,3,9,J,K. Here who has the highest card on the right last card?. ... the winner is “1” with “A” on the right last card.    

PYTHON PROGRAMMING APPROACH
![python_6](https://user-images.githubusercontent.com/53232113/175851092-4a6562e3-da5f-41b4-a448-dd35a01b7b97.png)


1.	DEFINE STRUCTURES: dictionaries, arrays, etc.View code [here](coding/structure)

1.1.	  TWO arrays hand1 and hand2 with 5 elements each. Each element has the card represented with two characters: ‘2K’, the first is the number of the card and the second is the suit.

1.2.	define values for cards in a dictionary: dict_value={'2':2,'3':3,'4':4,'5':5,'6':6,'7':7,'8':8,'9':9,'T':10,'J':11,'Q':12,'K':13,'A':14}

1.3.	Define  suites for cards  in an array  suites : = ['S','H','D','C']

1.4.	create a dictionary to store hand values depending on play or game:  Hand = {"nothing":1, "onePair":2, "twoPairs":3,"threeKind": 4, "Straight":5,"Flush":6,"FullHouse":7,"FourKind":8,"StraightFlush":9,"RoyalFlush":10}

1.5.	Define values for first and second hand and initiatize it to zero in dictionary Value_hands = {‘FirstHand’:0,’SecondHand’:0}

1.6.	Define totals  for first and second hand and initiatize it to zero in dictionary totals = {‘FirstHand’:0,’SecondHand’:0}

1.7.	Define hiCards  for first and second hand and initiatize it to zero in dictionary hiCards = {‘FirstHand’:0,’SecondHand’:0}

1.8.	Define a dictionary to store number of cards per suite in a game and initialize it to zero:
no_Suites = {'spadeSum':0,'heartSum':0, 'diamondSum':0,'clubSum': 0}

1.9.	Create a temporary  dictionary to store: “ total: and “hicard” values with values zero: Hand_value = {‘total”:0,’hiCard’:0}

2.	CHECK IF CARDS ARE CORRECT.  This will check if cards have values according to cards. The numbers are from 2 to A and suites are S,H,D or C.  If this condition is not true, the program will send a number zero as a result with a message indicating that the cards are not correct, finishing the program.View code [here](coding/checkcards)


3.	EVALUATE HAND1 AND STORE RESULTS. View code [here](coding/hand1)


3.1.	With the array hand1,  initialize dictionary Hand_value.

3.2.	Uses a function "getValueOfHand" to find out  on which game is the hand, and  two other values "total" and "Hicard".

3.3.	Finally saves the value of the game in three dictionaries: 1- "Value_hands['FirstHand'], 2- totals['FirstHand'] and  3- hiCards['FirstHand']

4.	EVALUATE HAND2 AND STORE RESULTS. View code [here](coding/hand2)

4.1.	With the array hand2,  initialize dictionary Hand_value.

4.2.	Uses a function "getValueOfHand" to find out  on which game is the hand, and  two other values "total" and "Hicard".

4.3.	Finally saves the value of the game in three dictionaries: 1- "Value_hands['SecondHand'], 2- totals['SecondHand'] and  3- hiCards['SecondHand'].

5.	CHECK WHO WINS?. View code [here](coding/check)

   -	FUNCTION "whowins" has as inputs three dictionaries:  Value_hands, totals and hiCards, each has valuesin dictionaries on first hand and second hand.

    1. VAlue_hands:  values the game. The highest value has game 'RoyalFlash' which is '10' and the lowest value is "nothing" with a value of '1' (see dictionary Hand)

    2. totals: has the totals for game.  If game has one pair of 3's, the totals is 3*2 = 6 or if hand is [2C 3H 4C 5S 6D], totals is number of last card which is '6'.
    
    3. HighCard: is the highest card of hand. If ['2C','2D','2S','2H','TH'], there are two pairs, the high card is the last card('T') and represents a number '10'.
       
With these inputs the function evaluales who wins, first or second hand. If first hand wins it returns a number '1'. If second hand wins it returns a number "2".

6.	Print results:  ‘0’: IF CARD ARE INCORRECT, ‘1’ IF HAND1 WINS, ‘2’ IF HAND2 WINS.  View some examples:

['2C', '2D', '2S', '2H', 'TH'] ['3C', '3D', '3S', '3H', 'JH']
the winner is:  2
['3C', '3D', '3S', '3H', 'TH'] ['3C', '3D', '3S', '3H', 'JH']
the winner  is:  2
['3C', '3D', '3S', '2D', '2S'] ['4C', '4D', '4S', '4H', 'JH']
the winner  is:  2
['TC', 'JC', 'QC', 'KC', 'AC'] ['3C', '4C', '5C', '6C', '7C']
the winner  is:  1
['TC', 'TH', 'KC', 'KD', 'AC'] ['3C', '5D', '5C', '8S', '9H']
the winner  is:  1
['3C', '4H', '5D', '6S', '7C'] ['5C', '6D', '7C', '8S', '9H']
the winner  is:  2
['3C', '3D', '4H', '7S', '9D'] ['2S', '2C', 'JD', 'KH', 'AS']
the winner  is:  1
['2C', '2D', '4H', '7S', '9D'] ['2S', '2C', 'JD', 'KH', 'AS']
the winner  is:  2
['2C', '4D', '6H', '8S', 'AD'] ['2S', '3C', '9D', 'JH', 'KH']
the winner  is:  1

 View code [here](coding/print)



   



