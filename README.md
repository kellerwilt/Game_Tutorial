# Game_Tutorial
A basic command-line game, and a description of how it works
This game works by printing out a message, prompting the user to choose a response to the given scenario.
The game then gets the users answer and displays the results of their actions

```Python
def room(): 
```
"rooms" are written as functions, so that we can send the user to a previously visited room, without copy-pasting the whole thing.
```Python
    trapped = True
```
makes the variable we will use to end our while loops
```Python
    while trapped: 
        print 'You wake up in a strange room. There is a mirror, a table and a window. What do you do to escape?'
        temp = raw_input('Press enter to continue') 
```
gives the user time to read the text before throwing more stuff at them which might cause them to miss something
```Python
        print '' 
```
print out the options
```Python
        print 'A: Climb out the window'
        print 'B: Wait for someone to find you'
        print 'C: Climb through the mirror into the matrix'
        print 'D: Open the door'
        answer=raw_input('Which option do you choose (a,b,c,d)').upper() 
```
gets the user's chosen answer
```Python
        if answer == 'A':
            print 'The window is locked, and will not open' 
```
tells the user the outcome of the option they chose
```Python
        if answer == 'B':
            print 'You wait 15 days, and nobody arrives to help you'
        if answer == 'C':
            print "You dive through the mirror, and hurt your head. This mirror doesn't lead to the matrix"
        if answer == 'D': 
```
determines if the correct answer was given
```Python
            print 'They forgot to lock you in. You escape and enter a seemingly endless hallway.'
            trapped = False 
            temp = raw_input('Press enter to continue')
            break 
```
moves them to the next section
```Python
        temp = raw_input('Press enter to continue')
def hallway():
    in_hallway = True
    while in_hallway:
        print 'You look down the hallway, and it seems to go on forever. Along the walls, are doors, each one different from the next. What do you do?'
        temp = raw_input('Press enter to continue')
        print ''
        print 'A: Walk down the hallway to see where it leads'
        print 'B: Start trying doors to see where they go'
        print 'C: Go back to the room to see if you missed something'
        print 'D: Yell down the hall to see if anyone else is there'
        answer=raw_input('Which option do you choose (a,b,c,d)').upper()
        if answer == 'A':
            print 'You wander aimlessly for 10 minutes. You begin to realize the doors are repeating themselves, and that you have been going in circles.'
        if answer == 'B':
            print "You start going through the doors, they all lead to dreams you have had in the past. You eventually get to a door covered in a zebra stripe pattern. You open it and it leads to what looks like your house. You enter, out of curiousity."
            in_hallway = False
            temp = raw_input('Press enter to continue')
            break
        if answer == 'C':
            print "You enter the room again, and look everywhere you can, but you don't notice anything you didn't see before."
        if answer == 'D':
            print 'Your voice echoes eerily around you. You wait, but hear nothing but your own panicked breath.'
```
does the same thing again for the hallway
```Python
  def House()
    in_house = True
    is_tired = True 
    times_eaten = 0
```
variables to limit the number of times an option can be chosen
```Python
    while in_house:
        print "It's a perfect replica of your house, but no decisions jump out at you immediately."
        temp = raw_input('Press enter to continue')
        print ''
        print "A: Go to your kitchen and get something to eat"
        print "B: Go to the front door and leave"
        print "C: Go back to the hallway to see if you missed anything"
        print "D: Go to bed and see if this is all a dream"
        answer = raw_input('Which option do you choose (a,b,c,d)').upper()
        if answer == 'A':
            if times_eaten < 3:
```
if the user has chosen this option less than 3 times, displays this message
```Python
                print "You eat a normal meal, and nothing seems out of the ordinary"
                times_eaten += 1 
```
tells the computer how many times the user has chosen this option
```Python
            else: 
```
changes the outcome of this option if it has been chosen more than 3 times which adds a layer of realism to the game
```Python
                print "You have run out of food"
        if answer == 'B': 
```
determines if the answer was correct
```Python
            print "You go outside and I run out of ideas"
            in_house = False 
            break
```
breaks the loop
```Python
        if answer == 'C':
            print "The hallway looks exactly as it did before"
            hallway() 
```
if the user chooses to go back to the hallway, they repeat the entire decision making process for the hallway again.
        if answer == 'D':
            if is_tired: 
allows the user to sleep, if they haven't done so already
```Python
                print "You have a peaceful, unninterupted nap. Now that you are rested, you return to your investigation."
                is_tired = False 
```
prevents the user from sleeping again
```Python
            else:
                print "You lie in bed for some time, but are not tired enough to fall asleep."   
```
goes through all the 'rooms' we created
```Python
room()
hallway()
house()
print 'Congratulations! You have outlived my immagination!' 
temp = raw_input('Press enter to win') 
```
ends the game
