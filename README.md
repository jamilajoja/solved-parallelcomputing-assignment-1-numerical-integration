Download Link: https://assignmentchef.com/product/solved-parallelcomputing-assignment-1-numerical-integration
<br>
Activity: Numerical integration

The purpose of this assignment is for you to

<ul>

 <li>get started back in writing C or C++ code</li>

 <li>get familiar with running code on mamba</li>

 <li>write a simple program that will be reused in future assignments</li>

</ul>

As usual all time measurements are to be performed on the cluster.

<h1>1           Numerical Integration</h1>

Numerical integration is often used when one wants to computebut one does not know how to find a primitive of <em>f</em>. You can use the definition of integration to obtain a simple approximation by computing is often called the number of point in the approximation. (This is the

numerical integration using the rectangle rule. You can learn more at <a href="https://en.wikipedia.org/wiki/Numerical_integration">https://en.wikipedia.org/wiki/</a>

<a href="https://en.wikipedia.org/wiki/Numerical_integration">Numerical_integration</a><a href="https://en.wikipedia.org/wiki/Numerical_integration">.</a>)

The provided package contains multiple functions to integrate in libfunctions.a. The functions are named f1, f2, f3, f4, and take two parameters: the first one is a floating point number <em>x </em>where the function is computed, and the second one is <em>intensity </em>an operation intensity. The second parameter is used to make the function take more time.

The code you should write should take 5 command line parameters:

<ul>

 <li>functionid, an integer to know which function to integrate. If functionid is 1, integrate f1; If functionid is 2, integrate f2; etc.</li>

 <li>a, the lower bound of the integral</li>

 <li>b, the upper bound of the integral</li>

 <li>n, an integer which is the number of points to compute the approximation of the integral</li>

 <li>intensity, an integer which is the second parameter to give the the function to integrate. You will see that in the scaffold f1 takes two parameter, an <em>x</em>, and an <em>intensity</em>. Use that parameter as <em>intensity</em>.</li>

</ul>

The code should compute the integral and output the value of the integral on stdout (and nothing else). The code should also measure the time it took to compute the integral and write that time (expressed in seconds with decimal values) to stderr (and nothing else).

<strong>Question: </strong>Write the described code. You can use the provided archive as a template. It contain a template code and makefile to help you write the code. You should only need to complete main.cpp. You should be able to test if your code is correct using make test.

<h1>2           Benchmarking on mamba</h1>

<strong>Question: </strong>Report the time it takes on the cluster to integrate f1 using different number of points (from 10<sup>1 </sup>to 10<sup>8</sup>) and with different operation intensity (from 1 to 10<sup>4</sup>). To help you in that task, you should be able to run make bench which should run the benchmark in a PBS job. Once that job is completed, you can draw charts using make plot which reports time in a pdf file plot/time plots.pdf.

Make sure you keep this code around as it is your base for comparisons in future assignments.

1

<h1>FAQ</h1>

<strong>Do I need to understand how integration works?</strong>

Not really. The assignment is really about evaluating that particular expression. You don’t need to understand why that is an integration operation. The problem is just to evaluate for a particular combination of <em>a</em>, <em>b</em>, <em>n</em>, and <em>f</em>.

<strong>I can’t find the code of function f1, f2, f3, f4 ?!</strong>

Indeed, you don’t have access to them. You do not need access to the code of functions f1, f2, f3, and f4. These functions are in libfunctions.a.

<strong>When I compile, it does not find function f1.</strong>

Do not compile by hand, use make.

<strong>When I run make bench, it tells me “qsub command not found”.</strong>

You need to run make bench on mamba.

<strong>When I run make bench, it tells me I need to pass the tests.</strong>

You need to have successfully run make test.

<strong>How long will the job take to run?</strong>

The job may run on a mamba compute node for about an hour. (Depending on how the code is written). Note that you don’t need to stay logged on mamba. Once the job is batched, mamba will eventually run it.

<strong>How should I measure time?</strong>

Use std::chrono::system clock. Check cpprefence.

<strong>I get “error: unrecognized command line option ‘-std=c++17”’ when compiling on mamba </strong>Add module load gcc at the end of your /.bashrc on mamba.