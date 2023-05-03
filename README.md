Download Link: https://assignmentchef.com/product/solved-cs-457-assignment-4
<br>
Database Management Systems

<strong>Programming Assignment 4: Transactions </strong>

<h1>Overview</h1>

In this assignment you will write a program that allows a database user to enclose SQL statements into a transaction block. That is, you will implement the “all-or-nothing” property commonly seen in real-world database systems. This assignment assumes the basic metadata and data management have been implemented in the first three programming assignments.

<h1>System Design</h1>

<ul>

 <li>You will decide how to guarantee the atomicity of transactions o In demo lecture: locking o As always, you are free (in fact, encouraged) to come up with your own design</li>

 <li>In the design document, you should clearly explain how your program implements the atomicity property of transactions. The easiest way to do this is to declare lock variables shared between processes. For example, you can create an empty file called “&lt;table_name&gt;_lock” to indicate an existing process is accessing &lt;table_name&gt;. In this case, we also assume the procedure of creating the empty file is atomic: at any time, only one process is able to create/delete the lock file (recall the P/V operations in your operating system class). As a result, after a transaction starts, the system will first check the &lt;table_name&gt;_lock file before granting accesses to that specific table &lt;table_name&gt;. If there does exist such a lock file, then the system will reject/suspend the access request. Otherwise, everything works as before (e.g., updating tuples), except that <em>the change will not be persisted to the disk until a “commit” is encountered</em>.</li>

</ul>

<h1>Implementation</h1>

<ul>

 <li>The program should not use external database libraries, frameworks, or applications.</li>

 <li>Any programming language is acceptable, e.g., Python, Java, C/C++, Go o Just pick one(s) that you are most comfortable/proficient with

  <ul>

   <li>But keep in mind we will test your code in Linux with OS-level utilities (e.g., files) &#x25aa; So, probably not: C#, Object-C, JavaScript, Prolog…</li>

  </ul></li>

 <li>Functionalities:

  <ul>

   <li>SQL: Begin Transaction, Commit</li>

  </ul></li>

</ul>

<h1>Interface</h1>

<ul>

 <li>A similar but simpler interface than Sqlite3</li>

 <li>Same as homework #1: standard input, standard output (or files if you prefer) o This assignment the program will be tested using two (2) interactive terminals (to emulate two concurrent processes/clients).</li>

</ul>




<h1>Testing</h1>

<ul>

 <li>We will test your program on Ubuntu (version 14 or above)</li>

 <li>If your program cannot compile on our testbed, we may ask you to demo your program o Try not to use many exotic libraries.

  <ul>

   <li>The TA will probably not spend a whole day to setup an environment as yours.</li>

  </ul></li>

 <li>A full test script will be provided o We will NOT simply redirect the provided .sql file as standard input to your program</li>

</ul>

&#x25aa; Because there will be two clients/processes/terminals o Please, carefully read the comments in the given .sql file, and understand what the expected output means

<ul>

 <li>We will not to test your programs with any other scripts/commands</li>

</ul>

&#x25aa;   However, it’s always good to consider more edge cases

<h1>Grading (20 points)</h1>

<ul>

 <li>This is an individual assignment</li>

 <li>Design document that clarifies the followings: (5 points) o At a very high level, how you implement different joins.</li>

</ul>

o Be very specific on how to compile and execute your code

<ul>

 <li>Source code (15 points) o Coding style and clarity, 5 points

  <ul>

   <li>Appropriate parenthesis locations, indention, etc.</li>

   <li>Always write comments at the beginning of any files</li>

  </ul></li>

 <li>Author, date, history, etc.</li>

</ul>

&#x25aa;   Always write comments at the beginning of any non-trivial class/function

<ul>

 <li>What this class/function/subroutine does, high-level algorithm if needed

  <ul>

   <li>Write in-line comments for non-trivial blocks of code o Functionality, 10 points</li>

   <li>Refer to the test script for detailed breakdowns</li>

  </ul></li>

</ul>

<h1>Submission</h1>

<ul>

 <li>WebCampus</li>

 <li>Compress all your source code and documents into one package in this format:</li>

</ul>

o &lt;your_netid&gt;_pa4

<ul>

 <li>Late penalty: 10% per day</li>

</ul>


