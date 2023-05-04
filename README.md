Download Link: https://assignmentchef.com/product/solved-csci561-foundations-of-artificial-intelligence-homework-3
<br>
Image from imdb.com

<h1>Guidelines</h1>

<strong> </strong>

This is a programming assignment. You will be provided with sample inputs and outputs (see below). Please understand that the goal of the samples is to check that you can correctly parse the problem definition and generate a correctly formatted output. The samples are very simple and you should not assume that if your program works on the samples it will work on all test cases. There will be more complex test cases and it is your task to make sure that your program will work correctly on any valid input. You are encouraged to try your own test cases to check how your program would behave in some complex special case that you might think of. Since <strong>each homework is checked via an automated A.I. script</strong>, your output should match the example format <strong><em>exactly</em></strong>. Failure to do so will most certainly cost some points. The output format is simple and examples are provided. You should upload and test your code on vocareum.com, and you will submit it there. You may use any of the programming languages and versions thereof provided by vocareum.com.




<h1>Grading</h1>




Your code will be tested as follows: Your program should take no command-line arguments. It should read a text file called “input.txt” in the current directory that contains a problem definition. It should write a file “output.txt” with your solution. Format for files input.txt and output.txt is specified below. End-of-line convention is Unix (since vocareum is a Unix system).




The grading A.I. script will, 50 times:




<ul>

 <li>Create an input.txt file, delete any old output.txt file.</li>

 <li>Run your code.</li>

 <li>Compare output.txt created by your program with the correct one.</li>

 <li>If your outputs for all 50 test cases are correct, you get 100 points.</li>

 <li>If one or more test case fails, you <strong>lose 2 points for each failed test case</strong>. (note that one test case involves several answers in this HW; if any answer on a given test case is wrong, then the whole case is counted as wrong).</li>

</ul>




Note that if your code does not compile, or somehow fails to load and parse input.txt, or writes an incorrectly formatted output.txt, or no output.txt at all, or OuTpUt.TxT, <strong>you will get zero points</strong>. Please test your program with the provided sample files to avoid this. You can submit code as many times as you wish on vocareum, and the last submitted version will be used for grading.




<h1>Academic Honesty and Integrity</h1>




All homework material is checked vigorously for dishonesty using several methods. All detected violations of academic honesty are forwarded to the Office of Student Judicial Affairs. To be safe you are urged to err on the side of caution. Do not copy work from another student or off the web. Sanctions for dishonesty are reflected in <em>your permanent record</em> and can negatively impact your future success. As a general guide:




<strong>Do not</strong> <strong>copy</strong> code or written material from another student. Even single lines of code should not be copied.

<strong>Do not collaborate</strong> on this assignment. The assignment is to be solved individually.

<strong>Do not</strong> <strong>copy</strong> code off the web. This is easier to detect than you may think.

<strong>Do not share</strong> any custom test cases you may create to check your program’s behavior in more complex scenarios than the simplistic ones considered below.

<strong>Do not</strong> <strong>copy</strong> code from past students. We keep copies of past work to check for this. Even though this problem differs from those of previous years, do not try to copy from homework submissions of previous years.

<strong>Do not ask on piazza </strong>how to implement some function for this homework, or how to calculate something needed for this homework.

<strong>Do not post code on piazza </strong>asking whether or not it is correct. This is a violation of academic integrity because it biases other students who may read your post. <strong>Do not post test cases on piazza </strong>asking for what the correct solution should be.




<strong>Do</strong> ask the professor or TAs if you are unsure about whether certain actions constitute dishonesty. It is better to be safe than sorry.

<strong> </strong>

<strong> </strong>

<strong> </strong>

<h1>Project Description</h1>




You have finally found your dream job running an academy for puppies. You are so passionate about it, you worked long hours and your business is <em>booming</em>. There is only one problem: You have enlisted so many pups into your academy that you are starting to lose track of everything. Letting a puppy start the academy depends on their vaccination and health status. Even once they’re in, what they can train for and which other puppies they interact with depends on their history in the academy. Thankfully, you have a background in AI, so you decide to develop an automated system that can evaluate all of the information you have and alert you and your employees whether an action is possible. The system can also provide an instant guideline to keep owners informed and minimize the risks to these adorable puppies.




You sit down to develop a beta version of the system using <strong><em>first-order logic resolution</em></strong>. Puppy status and history data will be encoded as first order logic clauses in the knowledge base. The knowledge bases contain sentences with the following defined operators:

NOT X           ~X

X OR Y          X | Y

<h2>X AND Y    X &amp; Y X IMPLIES Y  X =&gt; Y</h2>

The program takes a query of n actions and provides a logical conclusion to whether each can be performed or not.




<strong><u>Format for input.txt:</u> </strong>

<strong> </strong>

&lt;N = NUMBER OF QUERIES&gt;

&lt;QUERY 1&gt;

…

&lt;QUERY N&gt;

&lt;K = NUMBER OF GIVEN SENTENCES IN THE KNOWLEDGE BASE&gt;

&lt;SENTENCE 1&gt;

…

&lt;SENTENCE K&gt;




The first line contains an integer <em>N</em> specifying the number of queries. The following <em>N</em> lines contain one query per line. The line after the last query contains an integer <em>K</em> specifying the number of sentences in the knowledge base. The remaining <em>K</em> lines contain the sentences in the knowledge base, one sentence per line.




<strong><em>Query format:</em></strong> Each query will be a single literal of the form Predicate(Constant_Arguments) or

~Predicate(Constant_Arguments) and will not contain any variables. Each predicate will have between 1 and 25 constant arguments. Two or more arguments will be separated by commas.




<strong><em>KB format:</em></strong> Each sentence in the knowledge base is written in one of the following forms:

<ul>

 <li>An <em>implication</em> of the form <em>p<sub>1</sub> </em>∧<em> p<sub>2</sub> </em>∧<em> … </em>∧<em> p<sub>m</sub> </em>⇒<em> q, </em>where its premise is a conjunction of literals and its conclusion is a single literal. Remember that a literal is an atomic sentence or a negated atomic sentence.</li>

 <li>A single literal: <em>q</em> or ~<em>q</em></li>

</ul>




Notes:

<ol>

 <li><sub>&amp;</sub> denotes the <em>conjunction</em></li>

 <li><sub>|</sub> denotes the <em>disjunction</em> It will not appear in the queries nor in the KB given as input. But you will likely need it to create your proofs.</li>

 <li><sub>=&gt;</sub> denotes the <em>implication</em></li>

 <li><sub>~</sub> denotes the <em>negation</em></li>

 <li>No other operators besides <sub>&amp;, =&gt;</sub>, and <sub>~</sub> are used in the knowledge base.</li>

 <li>There will be no parentheses in the KB except as used to denote arguments of predicates.</li>

 <li>Variables are denoted by a single lowercase letter.</li>

 <li>All predicates (such as Vaccinated) and constants (such as Hayley) are case sensitive alphabetical strings that begin with uppercase letters.</li>

 <li>Each predicate takes at least one argument. Predicates will take at most 25 arguments. A given predicate name will not appear with different number of arguments.</li>

 <li>There will be at most 10 queries and 100 sentences in the knowledge base.</li>

 <li>See the sample input below for spacing patterns.</li>

 <li>You can assume that the input format is exactly as it is described.</li>

 <li>There will be no syntax errors in the given input.</li>

 <li>The KB will be true (i.e., will not contain contradictions).</li>

</ol>




<strong><u>Format for output.txt:</u> </strong>




For each query, determine if that query can be inferred from the knowledge base or not, one query per line:




&lt;ANSWER 1&gt;

…

&lt;ANSWER N&gt;




Each answer should be either TRUE if you can prove that the corresponding query sentence is true given the knowledge base, or FALSE if you cannot.

<strong><u>Notes and hints:</u></strong>




<ul>

 <li>Please name your program “<strong>xxx</strong>” where ‘xxx’ is the extension for the programming language you choose. (“<strong>py</strong>” for python3, “<strong>cpp</strong>” for C++, and “<strong>java</strong>” for Java). If you are using C++11, then the name of your file should be “homework11.cpp” and if you are still using python2 even though it’s not supported anymore, then the name of your file should be “homework2.py”.</li>

 <li>If you decide that the given statement can be inferred from the knowledge base, every variable in each sentence used in the proving process should be unified with a Constant (i.e., unify variables to constants before you trigger a step of resolution).</li>

 <li>All variables are assumed to be universally quantified. There is no existential quantifier in this homework. There is no need for Skolem functions or Skolem constants.</li>

 <li>Operator priorities apply (negation has higher priority than conjunction). There will be no parentheses in the sentences, other than around arguments of predicates.</li>

 <li>The knowledge base is consistent.</li>

 <li>If you run into a loop and there is no alternative path you can try, report FALSE. An example for this would be having two rules <strong><em>(1)</em></strong> A(x) =&gt; B(x) and <strong><em>(2)</em></strong> B(x) =&gt; A(x) and wanting to prove A(Teddy). In this case your program should report FALSE.</li>

 <li>Note that the KB is not in Horn form because we allow more than one positive literal. So you indeed must use resolution and cannot use generalized Modus Ponens.</li>

</ul>




<strong><u>Example 1:</u> </strong>




For this input.txt:




1

Play(Hayley,Teddy)

6

Vaccinated(x) =&gt; Start(x)

Start(x) &amp; Healthy(x) =&gt; Ready(x)

Ready(x) &amp; Ready(y) =&gt; Play(x,y)

Vaccinated(Hayley)

Healthy(Hayley)

Healthy(Teddy)




your output.txt should be:




FALSE

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong><u>Example 2:</u> </strong>

<strong> </strong>

For this input.txt:




2

Learn(Sit,Ares)

Graduate(Hayley)

8

Ready(x) =&gt; Train(Come,x)

Healthy(x) &amp; Train(y,x) =&gt; Learn(y,x)

Learn(Come,x) =&gt; Train(Sit,x) Learn(Come,x) &amp; Learn(Sit,x) =&gt; Train(Down,x)

Learn(Down,x) =&gt; Graduate(x)

Ready(Hayley)

Ready(Ares)

Healthy(Ares)




your output.txt should be:




TRUE

FALSE




<strong><u>Example 3:</u> </strong>

<strong> </strong>

For this input.txt:




3

Play(Ares,Teddy)

Train(Down,Hayley)

Play(Ares,Hayley)

10

Healthy(x) =&gt; Ready(x)

Ready(x) =&gt; Train(Come,x)

Healthy(x) &amp; Train(y,x) =&gt; Learn(y,x)

Learn(Come,x) =&gt; Train(Sit,x) Learn(Come,x) &amp; Learn(Sit,x) =&gt; Train(Down,x)

Learn(Down,x) =&gt; Graduate(x)

Ready(x) &amp; Ready(y) =&gt; Play(x,y)

Healthy(Ares)

Healthy(Hayley) Learn(Come,Hayley)




your output.txt should be:




FALSE

TRUE

TRUE




<strong><u>Example 4:                              </u></strong><strong><u>(note: a previous typo has been corrected)</u></strong>

<strong> </strong>

For this input.txt:




5

Greet(Hayley,TrainerJosh)

PlayFetch(Luna,TrainerBibek)

ShowOff(Ares,TrainerChristina)

Graduate(Hayley)

Play(Leia,Teddy)

50

Vaccinated(x) =&gt; Start(x)

Start(x) &amp; Healthy(x) =&gt; Ready(x)

RespondToName(x) =&gt; Train(Come,x)

Ready(x) &amp; Train(y,x) =&gt; Learn(y,x)

Learn(Come,x) =&gt; Train(Sit,x)

Learn(Come,x) &amp; Learn(Sit,x) =&gt; Train(Down,x)

Learn(Sit,x) =&gt; Train(Paw,x)

Learn(Paw,x) &amp; Working(y) =&gt; Greet(x,y)

Scared(x,y) =&gt; ~Socialize(x,y)

Ready(x) &amp; Ready(y) &amp; Socialize(x,y) &amp; Socialize(y,x) =&gt; Play(x,y)

Learn(Get,x) =&gt; Train(Drop,x)

Learn(Come,x) &amp; HoldToy(x) =&gt; Train(Get,x)

RespondToName(x) &amp; HoldToy(x) =&gt; Train(Drop,x)

Learn(Come,x) &amp; Learn(Get,x) &amp; Learn(Drop,x) =&gt; Train(Fetch,x)

Learn(Fetch,x) &amp; Working(y) =&gt; PlayFetch(x,y) Learn(Down,x) =&gt; Train(Roll,x)

Learn(Roll,x) &amp; Working(y) =&gt; ShowOff(x,y)

RespondToName(x) &amp; Desensitized(Leash,x) =&gt; Train(WalkIndoors,x)

Learn(WalkIndoors,x) &amp; Desensitized(Cars,x) =&gt; Train(WalkOutdoors,x)

Learn(WalkOutdoors,x) &amp; Learn(Down,x) =&gt; Graduate(x)

~Sensitive(y,x) =&gt; Desensitized(y,x)

Sensitive(y,x) =&gt; TrainDesensitized (y,x)

Sensitive(y,x) &amp; TrainDesensitized(y,x) =&gt; Desensitized(y,x)

Vaccinated(Hayley)

Vaccinated(Ares)

~Vaccinated(Leia)

Vaccinated(Luna)

Vaccinated(Teddy)

~Healthy(Ares)

Healthy(Hayley)

Healthy(Luna)

Healthy(Leia)

Healthy(Teddy)

~Scared(Leia,Teddy)

Scared(Teddy,Leia)

~Sensitive(Leash,Hayley)

~Sensitive(Cars,Teddy)

Sensitive(Cars,Luna)

~Sensitive(Cars,Hayley)

Working(TrainerChristina)

~Working(TrainerJosh)

Working(TrainerBibek)

RespondToName(Hayley)

RespondToName(Luna)

RespondToName(Ares)

HoldToy(Luna)

~HoldToy(Leia)

~RespondToName(Leia)

Sensitive(Cars,Leia)










your output.txt should be:




FALSE TRUE

FALSE TRUE

FALSE