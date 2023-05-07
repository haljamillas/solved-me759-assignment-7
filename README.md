Download Link: https://assignmentchef.com/product/solved-me759-assignment-7
<br>
. (a) Implement in a file called matmul.cu the matmul and matmul kernel functions as declared and described in matmul.cuh.

<ul>

 <li>Write a program cu which does the following:

  <ul>

   <li>Creates matrices (as 1D row major arrays) A and B of size n*n in <em>managed (aka unified) memory</em>.</li>

   <li>Fills those matrices however you like.</li>

   <li>Calls your matmul</li>

   <li>Prints the last element of the resulting matrix.</li>

   <li>Prints the time taken to perform the multiplication in <em>milliseconds </em>using CUDA events.</li>

   <li>Compile: nvcc task1.cu matmul.cu -Xcompiler -O3 -Xcompiler -Wall -Xptxas -O3 -o task1</li>

   <li>Run (where n and threads per block are positive integers): ./task1 n threads per block</li>

   <li>Example expected output:</li>

  </ul></li>

</ul>

11.36

1.23

<ul>

 <li>On an Euler <em>compute node</em>, run task1 for each value n = 2<sup>5</sup><em>,</em>2<sup>6</sup><em>,</em>·· <em>,</em>2<sup>15 </sup>and generate a plot task1.pdf which plots the time taken by your algorithm as a function of n when threads per block = 1024. Overlay another plot which plots the same relationship with a different choice of threads per block.</li>

</ul>

1

<ol start="2">

 <li>(a) Implement in a file called stencil.cu stencil and stencil kernel functions as declared and described in stencil.cuh. These functions should produce the 1D convolution of image and mask:</li>

</ol>

<em>R </em>output[<em>i</em>] = <sup>X </sup>image[<em>i </em>+ <em>j</em>] ∗ mask[<em>j </em>+ <em>R</em>]     <em>i </em>= 0<em>,</em>··· <em>,</em>n − 1

<em>j</em>=−<em>R</em>

Assume that image[<em>i</em>] = 0 when <em>i &lt; </em>0 or <em>i &gt; </em>n − 1. Pay close attention to what data you are asked to store and compute in shared memory.

<ul>

 <li>Write a program cu which does the following:

  <ul>

   <li>Creates arrays image (length n), output (length n), and mask (length 2 * R + 1) all in <em>managed memory</em>.</li>

   <li>Fills those arrays however you like.</li>

   <li>Calls your stencil</li>

   <li>Prints the last element of the resulting array.</li>

   <li>Prints the time taken to perform the convolution in <em>milliseconds </em>using CUDA events.</li>

   <li>Compile: nvcc task2.cu stencil.cu -Xcompiler -O3 -Xcompiler -Wall -Xptxas -O3 -o task2</li>

   <li>Run (where n, R, and threads per block are positive integers):</li>

  </ul></li>

</ul>

./task2 n R threads per block

<ul>

 <li>Example expected output:</li>

</ul>

11.36

1.23

<ul>

 <li>On an Euler <em>compute node</em>, run task2 for each value n = 2<sup>10</sup><em>,</em>2<sup>11</sup><em>,</em>·· <em>,</em>2<sup>31 </sup>and generate a plot task2.pdf which plots the time taken by your algorithm as a function of n when threads per block = 1024 and R = 128. Overlay another plot which plots the same relationship with a different choice of threads per block.</li>

</ul>