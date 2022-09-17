# hANGMAN-gaME

import random
print("Welcome to Hangman Game"+'''
 _                                            
| |                                            
| |__   __ _ _ __   __ _ _ __ ___   __ _ _ __  
| '_ \ / _` | '_ \ / _` | '_ ` _ \ / _` | '_ \ 
| | | | (_| | | | | (_| | | | | | | (_| | | | |
|_| |_|\__,_|_| |_|\__, |_| |_| |_|\__,_|_| |_|  
                    __/ |                      
                   |___/                      
  
''')
stages=['''

 +---+
  |   |
  O   |
 /|\  |
 / \  |
      |
=========


''',
'''
    +---+
  |   |
  O   |
 /|\  |
 /    |
      |
=========

  
  
  
  ''',
  '''
  
    +---+
  |   |
  O   |
 /|\  |
      |
      |
=========
  
  
  
  ''','''
    +---+
  |   |
  O   |
 /|   |
      |
      |
=========
  
  
  ''',
'''
  +---+
  |   |
  O   |
  |   |
      |
      |
=========




''',
'''
  +---+
  |   |
  O   |
      |
      |
      |
=========



''',
'''
  +---+
  |   |
      |
      |
      |
      |
=========  
  
  
  
  ''']

word_list = [
'abruptly', 
'absurd', 
'abyss', 
'affix', 
'askew', 
'avenue', 
'awkward', 
'axiom', 
'azure', 
'bagpipes', 
'bandwagon', 
'banjo', 
'bayou', 
'beekeeper', 
'bikini', 
'blitz', 
'blizzard', 
'boggle', 
'bookworm', 
'boxcar', 
'boxful', 
'buckaroo', 
'buffalo', 
'buffoon', 
'buxom', 
'buzzard', 
'buzzing', 
'buzzwords', 
'caliph', 
'cobweb', 
'cockiness', 
'croquet', 
'crypt', 
'curacao', 
'cycle', 
'daiquiri', 
'dirndl', 
'disavow', 
'dizzying', 
'duplex', 
'dwarves', 
'embezzle', 
'equip', 
'espionage', 
'euouae', 
'exodus', 
'faking', 
'fishhook', 
'fixable', 
'fjord', 
'flapjack', 
'flopping', 
'fluffiness', 
'flyby', 
'foxglove', 
'frazzled', 
'frizzled', 
'fuchsia', 
'funny', 
'gabby', 
'galaxy', 
'galvanize', 
'gazebo', 
'giaour', 
'gizmo', 
'glowworm', 
'glyph', 
'gnarly', 
'gnostic', 
'gossip', 
'grogginess', 
'haiku', 
'haphazard', 
'hyphen', 
'iatrogenic', 
'icebox', 
'injury', 
'ivory', 
'ivy', 
'jackpot', 
'jaundice', 
'jawbreaker', 
'jaywalk', 
'jazziest', 
'jazzy', 
'jelly', 
'jigsaw', 
'jinx', 
'jiujitsu', 
'jockey', 
'jogging', 
'joking', 
'jovial', 
'joyful', 
'juicy', 
'jukebox', 
'jumbo', 
'kayak', 
'kazoo', 
'keyhole', 
'khaki', 
'kilobyte', 
'kiosk', 
'kitsch', 
'kiwifruit', 
'klutz', 
'knapsack', 
'larynx', 
'lengths', 
'lucky', 
'luxury', 
'lymph', 
'marquis', 
'matrix', 
'megahertz', 
'microwave', 
'mnemonic', 
'mystify', 
'naphtha', 
'nightclub', 
'nowadays', 
'numbskull', 
'nymph', 
'onyx', 
'ovary', 
'oxidize', 
'oxygen', 
'pajama', 
'peekaboo', 
'phlegm', 
'pixel', 
'pizazz', 
'pneumonia', 
'polka', 
'pshaw', 
'psyche', 
'puppy', 
'puzzling', 
'quartz', 
'queue', 
'quips', 
'quixotic', 
'quiz', 
'quizzes', 
'quorum', 
'razzmatazz', 
'rhubarb', 
'rhythm', 
'rickshaw', 
'schnapps', 
'scratch', 
'shiv', 
'snazzy', 
'sphinx', 
'spritz', 
'squawk', 
'staff', 
'strength', 
'strengths', 
'stretch', 
'stronghold', 
'stymied', 
'subway', 
'swivel', 
'syndrome', 
'thriftless', 
'thumbscrew', 
'topaz', 
'transcript', 
'transgress', 
'transplant', 
'triphthong', 
'twelfth', 
'twelfths', 
'unknown', 
'unworthy', 
'unzip', 
'uptown', 
'vaporize', 
'vixen', 
'vodka', 
'voodoo', 
'vortex', 
'voyeurism', 
'walkway', 
'waltz', 
'wave', 
'wavy', 
'waxy', 
'wellspring', 
'wheezy', 
'whiskey', 
'whizzing', 
'whomever', 
'wimpy', 
'witchcraft', 
'wizard', 
'woozy', 
'wristwatch', 
'wyvern', 
'xylophone', 
'yachtsman', 
'yippee', 
'yoked', 
'youthful', 
'yummy', 
'zephyr', 
'zigzag', 
'zigzagging', 
'zilch', 
'zipper', 
'zodiac', 
'zombie', 
]

# word_list=["advark", "baboon", "camel",'aardvark', 'anteater', 'antelope', 'albert','woof', 'meow','My', 'very', 'energetic', 'mother', 'just', 'served', 'us', 'nachos.']
chosen_word=random.choice(word_list)

lives=6
# print(f"THe chosen words is :{chosen_word}")

display=[]
for blank in range(len(chosen_word)):
  display+="_"
print(display)
end_of_game=False
while not end_of_game:
    Guess_letter=input("Guess a letter: ").lower()
    if Guess_letter in display:
      print(f"You already Guessed {Guessed_letter}")
    for position in range(len(chosen_word)):
      letter = chosen_word[position]
      if letter==Guess_letter:
        display[position]=letter
    if Guess_letter not in chosen_word:
      print(f"{Guess_letter} not in word.YOU lose a life")
      lives-=1
      if lives==0:
        end_of_game=True
        print("you lose")
    print(display)
    if "_" not in display:
      end_of_game=True
      print("YOU WON, END OF GAME")
    print(stages[lives])
    
    
    
    
    OUTPUT:
    
    
    Welcome to Hangman Game
 _                                            
| |                                            
| |__   __ _ _ __   __ _ _ __ ___   __ _ _ __  
| '_ \ / _` | '_ \ / _` | '_ ` _ \ / _` | '_ \ 
| | | | (_| | | | | (_| | | | | | | (_| | | | |
|_| |_|\__,_|_| |_|\__, |_| |_| |_|\__,_|_| |_|  
                    __/ |                      
                   |___/                      
  

THe chosen words is :jukebox
['_', '_', '_', '_', '_', '_', '_']
Guess a letter: m
m not in word.YOU lose a life
['_', '_', '_', '_', '_', '_', '_']

  +---+
  |   |
  O   |
      |
      |
      |
=========




Guess a letter: b
['_', '_', '_', '_', 'b', '_', '_']

  +---+
  |   |
  O   |
      |
      |
      |
=========




Guess a letter: d
d not in word.YOU lose a life
['_', '_', '_', '_', 'b', '_', '_']

  +---+
  |   |
  O   |
  |   |
      |
      |
=========





Guess a letter: q
q not in word.YOU lose a life
['_', '_', '_', '_', 'b', '_', '_']

    +---+
  |   |
  O   |
 /|   |
      |
      |
=========
  
  
  
Guess a letter: 
['_', '_', '_', '_', 'b', '_', '_']

    +---+
  |   |
  O   |
 /|   |
      |
      |
=========
  
  
  
Guess a letter: X
['_', '_', '_', '_', 'b', '_', 'x']

    +---+
  |   |
  O   |
 /|   |
      |
      |
=========
  
  
  
Guess a letter: F
f not in word.YOU lose a life
['_', '_', '_', '_', 'b', '_', 'x']

  
    +---+
  |   |
  O   |
 /|\  |
      |
      |
=========
  
  
  
  
Guess a letter: E
['_', '_', '_', 'e', 'b', '_', 'x']

  
    +---+
  |   |
  O   |
 /|\  |
      |
      |
=========
  
  
  
  
Guess a letter: Q
q not in word.YOU lose a life
['_', '_', '_', 'e', 'b', '_', 'x']

    +---+
  |   |
  O   |
 /|\  |
 /    |
      |
=========

  
  
  
  
Guess a letter:         
     not in word.YOU lose a life
you lose
['_', '_', '_', 'e', 'b', '_', 'x']


 +---+
  |   |
  O   |
 /|\  |
 / \  |
      |
=========

    
