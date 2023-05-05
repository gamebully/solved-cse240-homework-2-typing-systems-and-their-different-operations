Download Link: https://assignmentchef.com/product/solved-cse240-homework-2-typing-systems-and-their-different-operations
<br>



Introduction

The aim of this assignment is to make sure that you understand and are familiar with the concepts covered in the lectures, including programming paradigms, the structure of programming languages, and the differences between a macro and a procedure. By the end of the assignment, you should have

<ul>

 <li>exercised typing systems and operations of different typing systems.</li>

 <li>understood differences between the execution models of a macro and a function.</li>

 <li>gotten started with the programming environments Visual Studio and GCC.</li>

</ul>

This assignment is related to the outcomes 1-2 and 1-3 listed in the syllabus:

<ul>

 <li>learn strong vs. weak typing in computer programming languages</li>

 <li>understand the control structures of functional, logic, and imperative programming languages.</li>

 <li>understand the execution of functional, logic, and imperative programming languages.</li>

</ul>

<strong>Reading</strong>:​ Read chapter 1, chapter 2 (sections 2.1, 2.2, and 2.3), appendix (sections B.1 and B.2), and course notes (slides).

You are expected to do the majority of the assignment outside the class meetings. Should you need assistance, or have questions about the assignment, please contact the instructor or the TA during their office hours.

You are encouraged to ask and answer questions on the course discussion board. (However, <strong>do</strong>​<strong> not share your answers</strong> in the course discussion board.)​

<strong>Pre-requisite  </strong>

See Homework 1. Install Visual Studio on your computer or use computers in BYENG214 lab.

<h1>Programming Exercise</h1>

<ol>

 <li>Review the lecture slides which discuss Very Simple Programming Languages (VSPL). Next, observe the VSPL defined below and identify which sequences are valid.</li>

</ol>




<table width="0">

 <tbody>

  <tr>

   <td width="96">&lt;letter&gt;</td>

   <td width="456">::= a | b | c | d | e</td>

  </tr>

  <tr>

   <td width="96">&lt;LETTER&gt;</td>

   <td width="456">::= V | W | X | Y | Z</td>

  </tr>

  <tr>

   <td width="96">&lt;number&gt;</td>

   <td width="456">::= 0 | 2 | 3 | 4 | 8</td>

  </tr>

  <tr>

   <td width="96">&lt;letters&gt;</td>

   <td width="456">::= &lt;letter&gt; | &lt;letter&gt; &lt;letters&gt;</td>

  </tr>

  <tr>

   <td width="96">&lt;LETTERS&gt;</td>

   <td width="456">::= &lt;LETTER&gt; | &lt;LETTER&gt; &lt;LETTERS&gt;</td>

  </tr>

  <tr>

   <td width="96">&lt;numbers&gt;</td>

   <td width="456">::= &lt;number&gt; | &lt;number&gt; &lt;numbers&gt;</td>

  </tr>

  <tr>

   <td width="96">&lt;sequence&gt;</td>

   <td width="456">::= &lt;letters&gt; &lt;LETTERS&gt; &lt;numbers&gt; | &lt;LETTERS&gt; &lt;letters&gt; &lt;numbers&gt;</td>

  </tr>

 </tbody>

</table>

Which of the following are valid sequences? You must clearly identify for each of the following sequences, which are valid and which are invalid. Each sequence is worth 1 point. Submit your answer as hw02q1.pdf. [10 points]




<ol>

 <li>XYZcde348</li>

 <li>aZ20</li>

 <li>VWXa84</li>

 <li>edc135790V</li>

 <li>abcXYZ123</li>

 <li>dYaZeWkZ</li>

 <li>CSE240</li>

 <li>XYZabc22</li>

 <li>Ey542</li>

 <li>Zbad88</li>

</ol>

<ol start="2">

 <li>Read text section 1.4.2. Macros are available in most high-level programming languages. The body of a macro is simply used to replace a macro-call during the preprocessing stage. A macro introduces a “true inline” function that is normally more efficient than an “out-line” function. However, macros suffer from the side-effect, unwanted, or unexpected modifications to variables. Macros should be used cautiously. The main purpose of the following programs is to demonstrate the differences between a function and a macro. Other purposes include demonstrating the differences between different programming environments, and learning different ways of writing comments, formatted input and output, variable declaration and initialization, unary operation ++, macro definition/call, function definition/call, if-then-else and loop structures, etc.</li>

</ol>

Observe each of the functions below and understand their functionality. You can use either GNU gcc under Unix or Visual Studio to implement the code in this question

<table width="0">

 <tbody>

  <tr>

   <td width="601">int​ addf(​int​ a​ , ​ int​ ​ b​ )​ {            return​ ​a​ + ​b​;} int​ cubef(​int​ ​a​) {<sup>          </sup>return​ ​a​ * ​a​ * ​a​;} int​ minf(​int​ ​a​, ​int​  ​b​) {if​ (​a​ &lt;= ​b​) {            return​ ​a​;}else​ {             return​ ​b​;}} int​ evenf(​int ​ a​ )​ {<sup>         </sup>if​ (​a​ % 2 == 0) {            return​ 1;}else​ {             return​ 0;}</td>

  </tr>

 </tbody>

</table>

<ul>

 <li>Write four macros to re-implement the given four functions. Name them: addm, cubem, minm, and evenm, respectively. [10 points]</li>

 <li>Make a C file having the four functions and four macros defined in previous question. Write a main function to test the functions and macros. Use the following test cases in the main function to call your functions and macros in this order: [5 points] int a = 6, b = 8;addf(a, b);addm(a, b);addf(a++, b–);a = 6, b = 8;</li>

</ul>

addm(a++, b–);

a = 6, b = 8;cubef(a);cubem(a);cubef(–a);a = 6, b = 8;

cubem(–a);

a = 6, b = 8;

minf(a, b);minm(a, b);minf(–a, –b);a = 6, b = 8;

minm(–a, –b);

a = 6, b = 8;evenf(a);evenm(a);evenf(a++);a = 6, b = 8;

evenm(a++);

You must insert print statements to print every function call and macro above, so that the expected output looks like the following:

Your output should have actual answers, not zeros! Take a screenshot of the output. Mark the outputs in color where the function and corresponding macro generated different outputs. Submit in a PDF file hw02q2.pdf.

For questions 2.1 and 2.2, submit your program labeled as hw02q2.c and the output file hw02q2.pdf

<ol start="3">

 <li>You are given a file named hw02q3.c. All instructions are given in the form of comments in the file. You are to again run the file in <strong>both</strong>​ GCC​ and Visual Studio (2017 or 2015 version). Observe the outputs and make changes as asked. Please read all instructions very carefully, then complete and submit the updated file as hw02q3.c.</li>

</ol>