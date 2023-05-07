Download Link: https://assignmentchef.com/product/solved-fe520-homework-3
<br>
<h1>1          Class practice</h1>

<h2>1.1        Define class</h2>

Create a class called Rectangular, with two data attributes: length and width. They should be assigned in constructor ( init ()) It should also have two function attributes called area() and perimeter() which return area and perimeter of this rectangular respectively. Here is an example of the class structure:

&gt;&gt;&gt; class Rectangular:

…                      &lt;Your initializer&gt;

…                     &lt;Defination of area()&gt;

…                      &lt;Defination of perimeter()&gt;

&gt;&gt;&gt; myRec = Rectangular(10,20)

&gt;&gt;&gt; print(myRec.area())

200

&gt;&gt;&gt; print(myRec.perimeter())

60

<h2>1.2        Numpy applying on class</h2>

<ol>

 <li>define two numpy array with size 10, named with length and width.</li>

 <li>test your your class Rectangular with input as np array. (Here you should have 10 output for area and perimeter).</li>

</ol>

<h1>2          Display Time</h1>

Create a Time class and initialize it with hours, minutes and seconds.

<ol>

 <li>Make a method addTime which should take two time object and add them. E.g. if your original initial parameter is (2 hour and 50 min and 10 seconds), then you could call this method with another input parameters (1 hr and 20 min and 5 seconds) , then output is (4 hr and 10 min and 15 seconds)</li>

 <li>Make a method displayTime which should print the time (the initial parameter).</li>

 <li>Make a method DisplaySecond which should display the total seconds in the Time. E.g.- (1 hr 2 min) should display 3720 seconds.</li>

</ol>

<h1>3          UniformDistributedRandomNumberGenerator(50pt)</h1>

You can not use any random number generators in packages like Numpy, because you are required to build your own generator in this question.

Almost all the random numbers generated by computer are pseudo random numbers, because they are generated by a formula. A good random number generator is very important for financial simulations, such as Monte-Carlo method.

The goal of this assignment is to let you understand how computer generate random numbers and create pseudo random number generators which can generate 0-1 uniform-distributed random numbers by yourselves.

The probability density function (PDF) of 0-1 <a href="https://en.wikipedia.org/wiki/Uniform_distribution_(continuous)">uniform distribution</a> is

<sup></sup><sub> </sub>1    <em>for x </em>∈ [0,1]

<em>f</em>(<em>x</em>) =

<sup></sup><sub> </sub>0     <em>otherwise</em>

It means each point in interval [0,1] has the same probability to be chosen.

<ol>

 <li>For implementation purpose, people use different algorithms to generate pseudorandom numbers. One of the most famous algorithms is called <a href="https://en.wikipedia.org/wiki/Linear_congruential_generator">Linear Congru</a><a href="https://en.wikipedia.org/wiki/Linear_congruential_generator">ential Generator</a><a href="https://en.wikipedia.org/wiki/Linear_congruential_generator">(</a>LCG). This generator can yield a sequence of random numbers {<em>X<sub>i</sub></em>}. The recurrence relation of this algorithm is:</li>

</ol>

<em>X<sub>n</sub></em><sub>+1 </sub>= (<em>aX<sub>n </sub></em>+ <em>c</em>) <em>mod M</em>

here <em>a</em>, <em>c</em>, <em>M </em>are all parameters. <em>a </em>is called multiplier which satisfies 0 &lt; <em>a </em>&lt; <em>M</em>, <em>c </em>is called increment which satisfy 0 6 <em>c </em>&lt; <em>M</em>, <em>M </em>is the modulus which is also stands for the maximum range of this sequence. You can find more information about the common parameters setting in the link above. There is another parameter <em>X</em><sub>0 </sub>which is so called seed. You can generate totally different sequence by different seeds. In the formula above <em>mod </em>stands for the modulus operation, for example: 7 <em>mod </em>3 = 1 due to 7 = 2 × 3 + 1.

As you can guess, this generator can generate a sequence of integers within [0, <em>M</em>). To create a uniform distributed sequence, you only need to divide the sequence above by <em>M</em>.

For example, now I have a setting: <em>X</em><sub>0 </sub>= 1, and <em>a </em>= 1103515245, <em>M </em>= 2<sup>32</sup>, <em>c </em>= 12345.

<em>X</em><sub>1 </sub>=(<em>a </em>· <em>X</em><sub>0 </sub>+ <em>c</em>) <em>mod M </em>= 1103527590

<em>X</em><sub>2 </sub>=(<em>a </em>· <em>X</em><sub>1 </sub>+ <em>c</em>) <em>mod M </em>= 25248852323

…

Then the uniform distributed sequence will be

There are some variants of LCG, one of them has such recurrence relation:

<em>X<sub>n</sub></em><sub>+1 </sub>= (<em>X<sub>n</sub></em>(<em>X<sub>n </sub></em>+ 1)) <em>mod M</em>

The seed of this generator has to satisfy <em>X</em><sub>0 </sub><em>mod </em>4 = 2. Now it’s your turn to implement it in Python 3.

<ul>

 <li>(15 pt) Create a file called generator.py. In this file, create a class called LCG whose instance can generate random numbers by Linear Conguential Generator algorithm. It should have these data attributes: self.seed, self.multiplier, self.increment, self.modulus which are assigned in initializer ( init ()). The parameters should be passed by argument from outside of the class. This class’s instance should also at least have function attributes allow me: 1) get the seed; 2) set the seed; 3) initialize the generator (start from the seed); 4) give me the next random number; 5) give me a sequence (list) of random number, the length should be passed by argument.</li>

 <li>(10 pt) In generator.py, create an inherited class called SCG from class</li>

</ul>

LCG you have created. You are required to implement the variant of LCG I mentioned above in this class. It should have the same interfaces (attributes) with LCG, but different recurrence relation. Remember the seed of this generator has to satisfy <em>X</em><sub>0 </sub><em>mod </em>4 = 2, so you need to check this condition in initializer, raise error with customized error information if the seed doesn’t satisfy this condition.

Hint: To better reuse your code, your class should have a function attribute to specify the recurrence relation. You can only override this function in your inherited class.

<ul>

 <li>A good code style like following good conventions, writing comment and doc string for your code will earn additional bonus.</li>

</ul>

<ol start="2">

 <li>To test the performance of your generator, one way is to use a simple MonteCarlo method to test it. Consider a square and its inscribed circle in a 2-D rectangular coordinate. The length of square and the diameter of the circle are 2, and the center of them are both origin of this coordinate. See 2.</li>

</ol>

Figure 1: <em>x</em><sup>2</sup>+<em>y</em><sup>2 </sup>= 1, and its circumscribed square. Blue points are uniform distributed random points

You can populated the points in this 2-D coordinate within this square, and count the number of points which fall in the circle. Then dividing this number by the number of all points will give you an estimate of ratio of area between inscribed circle and its square . Since you have already have theoretical result of this ratio:

<em>ratio </em>

where <em>r </em>is the radius of the circle, thus the length of square is 2<em>r</em>. The closer your result is to this ratio, the better your random generator performs.

Now you need to use Python to do this:

<ul>

 <li>(15 pt) Create a file called point.py. Write a class to represent the points in rectangular coordinate. It should have the data attributes that store its</li>

</ul>

x coordinate and y coordinate, and also a function attribute distance to calculate its distance from origin point.

<ul>

 <li>(10 pt) Create a file called MCTest.py. Import the classes you created above (generators and point) from Python modules. Populate 10,000,000 random points within this square. To do this, you only need to populate 2 × 10<sup>7 </sup>0-1 uniform distributed random numbers firstly, then re-scale them into [−1,1], and pair them into 1 × 10<sup>7 </sup> Test both generators.</li>

</ul>

Determine whether points are within the circle. Hint: You can do this by computing its distance from origin, if it is smaller than 1 (the radius), it is within the circle.

Give the estimate of above ratio, and the difference between yours and theoretical one.

<ul>

 <li>You are also encouraged to record the time consumed by your program. Hint: use time package.</li>

</ul>

For this question, you need to submit 3 file: generator.py, point.py and MCTest.py.