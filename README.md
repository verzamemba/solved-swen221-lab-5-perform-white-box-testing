Download Link: https://assignmentchef.com/product/solved-swen221-lab-5-perform-white-box-testing
<br>
<h1></h1>

The purpose of this lab is to perform <em>white-box testing </em>for a simple program implementing the fictional board game CONNECT. The given implementation contains a number of hidden bugs, and you must write test cases to uncover these. The Emma tool for reporting code coverage should be used to help with this.

<h1>1        CONNECT</h1>

Sam and Mel purchased the board game CONNECT from their local games store. The rules are:

“The game of CONNECT is played on a board divided into 16 squares, arranged in a 4×4 format.

There are two players: white and black. Each player starts with 8 tokens in their respective colour (i.e. white or black). Initially, the board is empty. Then, each player takes it in turn to place one of their tokens on the board. The first player to get four of their tokens in a straight line is the winner (note, diagonal lines don’t count). A player’s token is “captured” when it becomes sandwiched between two of the other player’s tokens; captured tokens are removed from the board and cannot be used again (note, diagonal sandwiches do not count). The game continues until one player is the winner.”

Sam and Mel are playing CONNECT. The following is the sequence of turns taken so far:

(after 1st turn)              (after 2nd turn)            (after 3rd turn)            (after 4th turn)

Here, Mel (white) placed the first piece to begin the game. After the 2nd turn, we see that Sam’s piece was captured by Mel using a <em>short capture </em>move. After the 3rd turn, we see that Sam has blocked Mel from winning. After the 4th turn, we see that Mel has captured another of Sam’s pieces, this time using a <em>long capture </em>move.

Mutual Capture. An interesting feature of CONNECT is that it allows for a <em>mutual capture </em>move. This is when both players capture a piece from their opponent at the same time. The following illustrates:

(after 1st move)          (after 2nd move)         (after 3rd move)        (during 4th move)

In the final move above, black places his token between the two white tokens, and his/her token is immediately captured by white. At the same time, one of the white tokens is sandwiched between two black tokens and is also captured.

Figure 1: Illustrating the Emma tool being run under Eclipse. Green lines indicate those have been covered by the tests, whilst red lines are those which were not covered. Finally, yellow lines indicates partial coverage which typically occurs for conditionals where e.g. only one side of the conditional is taken.

<h2>2      Emma</h2>

Emma is a <em>code </em>coverage tool: for a given test it will tell you how much of your code is covered by that test. Emma is already installed in Eclipse and should be easy to use.

To find the coverage for a test, right click on a JUnit test file, and select “coverage as” and then “JUnit test”. The JUnit tests will be run as normal, but in the lower window pane there are test coverage results for the whole program. You should navigate through the package/class hierarchy to find the class or methods you are interested in. You can see pecentage coverage results. By clicking a class or method name, that class will be opened in the main code window and test coverage will be shown graphically: lines highlighted green are covered by the executed tests, lines highlighted red are not covered, lines highlighted yellow are partially covered — that is, some statements on that line are covered and some aren’t. The screenshot below shows what this looks like.

<h2>3      Getting Started</h2>

To get started, download the file connect.jar from course website and import them into Eclipse. This provides an implementation of the CONNECT game which has a number of hidden problems. A very simple <em>Graphical User Interface (GUI) </em>is provided for playing a game of CONNECT:

To use the GUIw, run the class swen221.connect.Main as a “Java Application”. With the GUI, you can place tokens by clicking on a square and placing either a white token, or a black token.

<h2>4     What to do</h2>

The given implementation of CONNECT contains a number of subtle problems which have been specifically chosen as they are hard to spot. Whilst you could simply “eye-ball” the code in detail to find these problems, you will likely this difficult and time-consuming. Instead, the goal of this lab is to gain experience writing test cases to identify (and then eliminate) these problems. This is simulating a <em>white-box </em>testing environment where you have access to the source code and can exploit this knowledge to develop test cases with good <em>code coverage</em>.

You will notice that the provided tests class swen221.connect.tests.ConnectTests contains only <em>one </em>test case. Your job is to write more test cases based on the rules of the game and the implementation. If your test cases obtain <em>good code coverage </em>you should be able to easily identify and fix the problems. When you submit your code, it will be run against a <em>hidden </em>set of test cases and the scored reported. <em>However, you will not be given information about why any particular test failed</em>. Instead, you must think carefully about what should and should not be allowed in the game and develop test cases accordingly. The Emma tool can be used to help here, as it will tell you how much code coverage is obtained with your test cases.

HINT:               You do not need to test the class GraphicalUserInterface (as it is hard to do this).

HINT:      Using Emma, identify regions of code not covered by your tests. Then, add tests for them!

HINT:    Be sure to test for <em>invalid </em>moves as these should be detected and reported.

HINT:    The documentation provided for different methods indicates what they should and should not do.

HINT:      If you find code which cannot be reached, then ask: <em>where should it be used?</em>