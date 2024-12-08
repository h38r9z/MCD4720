java c
MCD4720 -   Fundamentals of C++
Assignment 3 - Trimester   2,   2024

   
   
   
Purpose
Object-Oriented   Programming (OOP), inheritance, references, and   pointers   are fundamental concepts   in   programming languages. This assignment
provides an opportunity for you to showcase your understanding of these   concepts and demonstrate your ability to utilise   them   effectively.
The assignment   relates to   Unit   Learning Outcomes   2, 3, 4   and   5.
   
   
Your   task
Complete the   individual tasks as detailed   in the   instructions   below.Your project   must   be submitted as a CLion   project,   including   all   headers   and   code files, and any appropriate text files to ensure the   program compiles   and   runs.
   
Value
30% of your total marks for the   unit
The assignment   is marked out   of   100   marks.
   
Word   Limit
No overall word   limit
   
Due   Date
11:55   pm   Monday 6 January 2025
Specification
For this assignment you will write a   program to   play a game   named Farkle. This   section   specifies the   required functionality of the   program.
Scenario   (Pairs   Card Game):
You are tasked with   implementing a computer-based version of the card game   Pairs,   designed   for 2 to 8 players.   Pairs   is a simple,   press-your-luck   game where   there   is   no winner,   only   one loser.   Players earn points   by collecting pairs or   by folding,   and   the first   player   to   accumulate   too   many points   is declared   the   loser!
To familiarise yourself   with the game mechanics, you can watch the following videos   on   how   to   play:
•         https://www.youtube.com/watch?v=bq7Em3p7oS0or
•       https://www.youtube.com/watch?v=rcV45WyiWqsor   online   rules   here:
•         https://crabfragmentlabs.com/pairs
•       https://files.rebel.pl/files/instrukcje/PairsCompanionBook.pdf
In your version, for the basic assignment you only need to   implement   a   2-player   game.
Basic   Game Play:
In this   implementation of the game, the computer acts as the dealer,   controlling   a   triangular   deck of cards. This deck consists of cards in   sizes   ranging   from   1x1   to   10x10,   totalling   55   cards.   Please note that this   is not a   standard   deck   of   playing   cards.
The   basic game play   is   as follows:
u Shuffling and   Discarding: Shuffle the deck and discard   (burn) five   cards facedown   into   the centre of the table to form. the start of the discard   pile.   Each   time you   reshuffle,   you will burn five additional cards. This increases the   difficulty for   players   trying   to   guess which cards   remain   in the   deck.
u Starting the   Round: At the   beginning of each   round, deal one card face   up to   each   player. The   player with the   lowest card will take the first turn.
If there   is a tie for the   lowest card, deal a second   card   to   the   tied   players   to   break   the tie.   If the second card   results   in a pair, discard   it   and   deal   another.
            Example:   In the diagram provided,   Player A shuffles the deck and discards   five
cards. She then deals one card to   each   player face   up.   Player   D   has the   lowest   card   (a 6)   and will   go first.
u Player Choices: On your turn, you   have two choices:   hit   (take   a   card)   or   fold   (end   the   round).
            If you catch a pair or choose to fold, the   round   ends,   and you   score   points.
            If neither occurs, the turn   passes to the   left.
u Hitting: When you choose to   hit, your goal   is to avoid   catching   a   pair.   If you   do   catch   a   pair, the   round ends, and you score points   equal to   the   rank   of the   paired   card.
            Example:   If you catch a   pair of 8s,   you score 8   points.   Keep one   of those   cards   aside face up to track your   score.
u Folding: You   may also choose to fold   instead of hitting.   This   ends   the   round   ,   and   you
must select the lowest card currently   in   play to   keep for   points. You   can   choose this   card   from any player's stack,   including your   own.
Folding can sometimes be a strategic choice,   depending   on   your   chances   of   catching   a   pair.
u Ending the   Round: As soon as one   player catches a   pair   or folds,   the   round   is   over.   Discard all the cards   in players’ stacks, face down   into   the   middle,   and   deal   another round.
Scoring cards (those cards that were kept   aside   for   points)   are   not   discarded.
u Reshuffling: When the deck runs out, just shuffle and   continue.   Pause the   deal,
reshuffle the discards, and   resume dealing where you   left off. (Remember   to   burn   five   cards.)
u Losing the Game: There   is   no overall winner; the game   concludes with   one   loser. The   game ends when a   player reaches the target score, which varies   depending   on the   number of players. The formula for determining the score is:   (60   ÷   number   of   players)   +   1.
For games with 7 or 8   players,   maintain the   score   at   11.
Players
2
3
4
5
6+
Score
31
21
17
13
11
For example,   in a 4-player game, the   loser is the first   player to score   16   points.
u Breaking a Tie:   If two or more players   tie for the   lowest   card,   deal   additional   cards   to   the   tied   players as tiebreakers.   If the tiebreakers also tie, continue dealing   until   one   player
has the   lowest card.
If a player catches a pair during this   process,   discard   the   paired   card   and   deal   a   replacement.   Note that players cannot   be   knocked out by   a   pair during   this   tiebreaker,   although they may end up with   several   extra   cards!
u Dealing Cards: Cards are dealt   in a   consistent   order,   starting with   the   first   player   and   continuing clockwise around the table. Tiebreaker cards are dealt   in the   same   order.
u Defining a   Pair: A pair consists of any two   cards   in   a   single   player’s   stack   that   share   the   same rank. The cards do   not have to   be   adjacent to   one   another.   Cards   from   other players of the same   rank do not count as   a   pair for the   purposes   of this game.
There are numerous variations to this basic gameplay,   some   of which you   may   choose to   implement as extra functionality for your assignment.
Class Implementation:
You   MUST   implement your program using the following classes, at   a   minimum. You   may   include more classes as appropriate for your game   design:
•         Player class:   Holds a player’s details,   including their name, score, turns   taken   and   collection of cards (the player’s   stack   in the   game).
•         Card class:   holds the card’s details   including its   rank, a visual   representation   of the   card   and   its status –   in the   deck:
u discarded,
u   dealt to   or
u   held   by a   player
•       Application class:   Contains   the   main() function   and   controls   the   overall   flow   of the   game.
You may include other relevant attributes   and   behaviours   in these   classes.
Player Capabilities:
The   Player must   be   able to:
•             Assign a   Name: The player is   prompted to enter   a   name   at   the   start   of the   game, which   will be   used in   all feedback   and   scoring.
•             Choose Actions: The player can decide to   either   hit   (take   a   card)   or fold   (end   the   round)   based on their current strategy and   risk assessment.
•             View Current   Hand: The   player can see their current   hand of cards,   including   any
scoring cards they have set aside, allowing them to   make   informed   decisions   during   their   turn.
•             Catch   Pairs: When the   player hits and catches   a   pair, they   should   receive   immediate   feedback   indicating their score based on the   rank of the   paired cards.
•             End the   Round: The player can   choose to   end the   round   voluntarily   by   folding,   at   which   point they must select the   lowest card from any   player’s   stack to   keep for   points.
•             Track   Points: The player must   be able to   see   their   current   score,   as well   as   the   target   score for the game based on the   number of   players.
•             Continue   Playing: The   player can continue playing   rounds   until they   either   reach the   target score and lose the game or choose   to   quit   at   any   point   during   the   game.
•             Quit the Game: The player   has the   option to   exit   the   game   at   any time, whether   during   a   round or after a game   has   concluded.
Card Characteristics:
The Cards   in the   game should:
•         Card Types: The deck consists of triangular cards categorized   by size,   specifically
ranging from   1x1   up to   10x10.   Each card type has a   unique   rank corresponding   to   its   size.
•         Total Cards: There are a total of 55   cards   in the   deck,   ensuring   a   diverse   range   of   gameplay experiences.
•         Card Values:   Each card's value   is determined   by   its size, with   larger cards   having
higher values. The   ranks   range from   1 to   10, with   1   being   the lowest and   10 being   the   highest.
•          Face-Up/Face-Down: Cards are dealt face up to   players at   the   start   of   each   round,   allowing for visible player interaction.   Discarded cards are   placed face   down   in the         middle of the table to maintain secrecy.
•          Discard   Pile:   Five cards are burned (discarded face   down)   at   the   start   of each   round   to   create a discard pile. This affects the   remaining   cards   in   play,   making   it   harder for
players to guess the   remaining cards   in the deck.
•          Reshuffling: When the deck runs out of cards,   it   is   reshuffled along with   the   discarded      cards, ensuring continuous gameplay.   Players must remember to   burn five   cards   during   reshuffling.
Game Application Requirements:
The Game Application   must:
•          Display the “how to   play” information at   the   start   of the game.
•         Create a player with   initial   card.
•          Display an appropriate and uncluttered   user interface,   providing   relevant   information to   the player   at   all   times.
•         Ask for and allow the   player to enter an option to   hit   or fold.
•         Ask for and allow the player to   select   extra   card(s).
•          Display the updated   player’s cards.
•          End the   round for the   player
•         Specify the   loser
•          Provide player stats at the end of the game   and   each   round   (if   loss,   and   score).
Task 1:   UML   DiagramsYou   are   required   to   draw   a   UML   diagram   for   this   project   to   help   structure   your program more effectively. You will need a   UML   diagram for   each   of the   classes you   include   in your game –   at   least   a   Player,   Dice,   and   Application   (main)   class.   The   diagram   should   show   all   the   relationships   between   the   classes.   You   do   have   a   progress   check   during   week   8,   please   check   the   marking guide.
Task 2:   Create and Display a Menu
Your initial task   is to   implement a menu system   that will   be   displayed   to   the   user.   Below   is   an   example of how the menu shou代 写MCD4720 - Fundamentals of C++ Assignment 3 - Trimester 2, 2024C/C++
代做程序编程语言ld appear.   In this   example,   option   [1]   has   been   selected,
To accomplish this, create a function called   runMenu() and   call   it from   the   main() function.Inside the   runMenu() function, ensure that the   user can select any of the   displayed options   as   often as they desire before ultimately ending   the   program.   It   is   important   to   validate   the   user's      input so that only the displayed options   can   be   chosen.
Each option should be processed   numerically for easier selection.   For   instance,   option   [1]   can   be associated with "Ending the Program," option   [2] with   "Displaying   'Game   Rules'   Information," and so   on.
By   implementing this menu system and   incorporating input validation, you   will   create   a   user-   friendly   interface that allows for easy navigation and   interaction within your   program.
Task 3: Read data from a   file   and display
Your next task   is to display the   rules of the game,   providing   detailed   information on   how   to   play.   This   information should   be displayed similarly to the example shown   here. You   can   accomplish      this by creating a function and calling   it from   the   runMenu()   function when   option   [2],   "Display         'Game Rules'   Information,"   is selected.
The function   responsible for displaying the game   rules should accept the filename
"gameRules.txt” as a parameter. This function should successfully   read   and   display the   data
from the specified file. You can download the "gameRules.txt" file from the   unit's   Moodle   page   and place   it in the appropriate folder to   be   read and   displayed.   However,   you   should   modify the   content and format of the file to suit your program's   needs.   Please   keep the file   content   short
(no   more than 300 words). You should use ChatGPT to   generate   text   for the   game   rules. After   generating the text from ChatGPT, copy and paste   it   into   a file   named   gameRules.txt.
Additionally,   include the   link   to your interaction with ChatGPT in   the   same file.
In the "gameRules.txt" file, make sure to   include your details,   such   as   the   trimester,   unit,   and   other relevant information.   Modify the content of the file as   necessary to   ensure   it   integrates            smoothly into your   program.
By   implementing this task and   incorporating the function to display the game   rules, you will   provide clear instructions on   how to   play the   game.
   
Task 4: Play Pairs   Game
Your task   is to enable two   players to engage in the   card   game   Pairs.   This   includes   creating   players, setting up a triangular deck of 55 cards,   and   providing   an   intuitive   interface.
The   players should be   able   to:
•             Enter the   names at the start, used   for feedback   throughout the   game.
•             Draw or fold cards during their turn, with   appropriate   feedback:
o    Drawing   risks   getting   a   pair and   scoring   points.
o    Folding allows them   to   take   the   lowest   card   in   play for   points.
•             Track scores continuously after each round,   showing   current   players   scores.
•             End the game when   a   player   reaches the   losing   score.
•             Receive game stats at the   end,   showing   rounds   played, final   scores,   and wins/losses.
•             Return to the main   menu   at   any time   or   after   the   game   ends.
Implementing these features ensures a simple and engaging gameplay   experience
Task 5: Display the Reflection Report
Your final task is to display the   reflection   report and all the   extra functionality   that you   have   implemented.
Create a function for this task and   call   it from   the   runMenu()   function,   when   option   this   option   is   selected.
   
Program Reflection
You   must also   provide a 300-word written   reflection of   your   object-oriented   design   and   how   well   you   believe   it was to implement. You should cover the following areas:
u   Discuss why you designed   it the way you   did:
            Explain the   reasoning behind the structure of your classes and   how they   relate   to   each   other?
            Describe   how this design   reflects an object-oriented (OO) approach?
u   Discuss   how well you were able to   code   it:
            Highlight any challenges or issues you encountered during   the   implementation   phase.
            Discuss   how you addressed these   issues, whether through debugging,   refactoring, or         seeking assistance.   Reflect on the effectiveness of your coding skills and   how well you   were able to translate your design   into functional code.
u Furthermore,   consider   how   you   would   improve   your   design   if   you   were   to   undertake   the   project   again.   Discuss   potential   modifications   to   make   your   solution   easier   to   implement,   more efficient, or better suited for   code   reuse.
u It    is    necessary    to      include    a      list      of    all      implemented      extra    functionalities      in      the      report   otherwise, will   not   be marked.This   document   must   be   included   in   the   same   folder   as   your   Clion   project.   It   should   be   a   Word   document   containing the reflection and the   final   version   of the   UML   diagrams.   Your   document   file   MUST be named as follows “   YourFistNameLastName_A2.docx”   .
Extra   Functionality
The   marking   criteria   indicates that you   should   make   some   individual   additions to this   in   order to   achieve the final   15% of the marks.
Following is a list of additional features you can include in your project, with the maximum number   of marks you   can   earn for each   one,   shown   in the   following   format   [x].   You   may   implement   one   or more features from the list. You will only score up to a maximum of   15% of   the total assignment   marks   in other words a   capped total of   15 marks,   and you   can   pick   up   to   4   as   a   maximum.
You should aim to add some   additional   creative   elements to   the   gameplay,   as   well   as   advanced   object-oriented design elements or advanced use of   pointers.
a.      Display the cards using ASCII art. You can use different   images   related to   a   theme   or   “pip”   patterns for the numbers.   [5]
b.    Allow the game to be   saved   and   restored   at   the   player’s   request.   [5]
c.      All data members   in one   class to   be   pointers.   [5]
d.      Using   pointers to access values from the   heap.   [5]
e.      Include   multiple   human   players   making the   game   playable   by   2 to   any   number of   people.   Each   player   must   track   their   own   score   and   display   their   name   and   game   score   when   required. At the   beginning   of the game, one   player   is   randomly   chosen   to   go first   then   the   players   take turns   in   clockwise   order.   The   game   is   played   in   rounds   in which   each   player   has a turn to get a   card   and   score   points.   [5]
f.       Allow the game to be played with computer   players. The   computer   player should   be   able to   make reasonably intelligent decisions for choosing scoring combinations and when to save   their   points. This   artificial   Intelligent   can   be   a set   of   rules that the   computer   player   checks   before making a   hit or fold. On a   computer   player’s turn,   the   process   should   be   automated   so that the human player   can   watch   the   results.   [5]You certainly do not have to implement   all   of the   above to   earn   marks   for   extra   functionality.   Just   remember the   maximum   number   of marks you   can earn   are   given   in   [x]   and   you   can   choose   up   to four.   It   is   up to you!


Assignment 2: Marking   Criteria [up   to   100 marks in   total]
Does the   program compile and   run? Yes or   No


1.    Assignment Progress   Check   [10]
1.1.                5% in   Week 8: class diagram (this can be hand-drawn). Note that the class diagram should
show   the   individual   classes   and   the   interactions   between   them.   Hand-drawn   for the   UML   diagrams are accepted for this stage but   not for final submission.
1.2.                5%   in   Week 9:   Code   of the two   classes   (Player and   Card)   and   create   an   object   for   each class.
2.      UML Diagrams [5]
2.1.             Progress check   [.]
2.2.                Correct structure used (Name, Attributes,   Behaviours) and   relationship   [1]
2.3.                Included the correct designations for public   (+)   and   private   (-)   [2]
2.4.                Include all   required variables and functions with meaningful   names   [2]
3.      Class Design [10]
3.1.             Player   Class   [3]
3.1.1.    Has an appropriate   header file   [1]
3.1.2.    Required data members and member functions   using   meaningful   names   [1]
3.1.3.   Contains only aspects that relate to a “player” (has no data members or member
functions that are   not directly related to   the   Player)   [1]
3.2.             Card   Class   [3]
3.2.1.    Has an appropriate   header file   [1]
3.2.2.    Required data members and member functions   using   meaningful   names   [1]
3.2.3.   Contains   only   aspects   that   relate   to   a   “die”   (has   no   data   members   or   member
functions that are   not directly related to   the   Die)   [1]


3.3.             Game Application   [4]
3.3.1.    Has an appropriate   header file   [2]
3.3.2.    Has appropriate variables and functions using   meaningful   names   [1]
3.3.3.   The main() function has appropriate function calls to   keep   it   uncluttered   [1]
4.      Functionality   [45]
4.1.             Create and display menu   repeatedly till   user exit.   [5]
4.2.             Display Game   Rules file, with correct validations.   [2.5]
4.3.             Display the   reflection   report when the option   is selected, with correct validations.   [2.5]
4.9.          Successful      implementation    of    action    processes    and    feedback    displayed    to    the
player   [5]
4.10.      Appropriate end game conditions triggered and show   the winner/loser   [5]
5.      Quality of   Solution and Code [10]
5.1.             Does the   program   perform. the functionality   in   an   efficient   and   extensible   manner?
Functions are not   too   long   [2]
5.2.             Has a well-designed OO   program been   implemented?   [4]
5.2.1.    More classes   been   used   [2]
5.2.2.    Program structures support and OO   design   [2]
5.3.             Has the   Programming Style. Guide been followed   appropriately?   [4]
5.3.1.   Appropriate commenting and code documentation [2]      5.3.2.   Correct formatting of code within *.h and *.cpp files   [2]
6.      Extra Functionality   [15]
You are allowed to pick up   to four of   the   following:
6.3.            All data members   in one class   to   be   pointers.   [5]
6.4.             Using   pointers to access values from the   heap.   [5]
6.5.             Include   multiple human   players   making the game playable   by   2   to   any   number   [5]
6.6.            Allow the game to be played with   computer   players   [5]




   

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
