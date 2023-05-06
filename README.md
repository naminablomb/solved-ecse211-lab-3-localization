Download Link: https://assignmentchef.com/product/solved-ecse211-lab-3-localization
<br>
<ol>

 <li>Design a system to localize the robot using ultrasonic and light sensors, where the robot should move to a known starting position.</li>

 <li>Evaluate the design and determine how well the system localizes the robot.</li>

</ol>

<h1>Design requirements</h1>

The following design requirements must be met:

<ul>

 <li>The system must localize the robot to the origin of the tiles grid system.</li>

 <li>Localization must use the ultrasonic sensor and, optionally, light sensors (see bonus).</li>

 <li>The robot must localize approximately to the 0° direction using the ultrasonic sensor.</li>

 <li>The robot must localize to the (1, 1) gridpoint and 0° using the ultrasonic/light sensor.</li>

 <li>The robot must wait for input once completing angle localization and orienting to 0°.</li>

</ul>







<h2>Demonstration</h2>

The design must satisfy the requirements by completing the demonstration outlined below.

<h3>Design presentation</h3>

Before demoing the design, your group will be asked some questions for less than 5 minutes. You will present your design and answer questions designed to test your individual understanding of the lab concepts. Each person will be graded individually.

You must present your workflow, an overview of the hardware design, and an overview of the software functionality. Visualizing software with graphics such as flow charts is valuable.

<strong>Demonstration procedure </strong>

As shown in<strong> Figure 1</strong>,​ the robot is placed along the 45° line (thick dotted) inside the bottom-left tile of the 4×4 field grid. The <strong>brown-colored</strong>​ walls​ represent walls used for the <strong>ultrasonic</strong>​<strong> localization</strong>.​ Please note that the robot could be placed in <strong>ANY</strong>​<strong> ORIENTATION</strong> and​ <strong>POSITION</strong>​ along this 45° line. For example, <strong>Figure</strong>​<strong> 2</strong> shows another orientation and position of the robot’s starting position compared to that in<strong> Figure 1</strong>​ .​




<strong>Figure 1.  Robot’s Starting Orientation A.       Figure 2.  Robot’s Starting Orientation B. </strong>







Indicate to the TA what version of the ultrasonic localization you would like to use. Upon completing the <strong>angle</strong>​<strong> localization</strong>,​ the robot should orient to its estimated 0° axis and the TA will measure the <em>orientation</em>​<em> error</em> with respect to its true 0° axis. Note that you should have a stopping criterion to ensure that the robot stays still while the <em>error</em>​<em> angle</em> is​ being measured (e.g. Button.waitForAnyPress()​ can be used to separate the two procedures).​

After the measurement is complete, the robot should then move to the (1, 1) point as shown in <strong>Figure 1</strong> and <strong>Figure</strong>​<strong> 2</strong>.​ Once <strong>ultrasonic/light</strong>​<strong> localization</strong> is​ performed at this point, two error quantities are measured by the TA: the <em>Euclidean</em>​<em> distance error</em> ϵ​ between the robot’s actual position (<strong>X</strong>​ ​<strong>F</strong>, <strong>Y</strong>​ ​<strong>F</strong>) and the (1, 1) point, and the <em>orientation error</em>​ ​ with respect to the 0° axis.​

​          ​

ε = √(<em>X<sub>F</sub></em>)<sup>2 </sup>+ (<em>Y<sub>F</sub></em>)<sup>2</sup>

<h3>Angle Localization</h3>

<ul>

 <li><strong>5 points </strong>are​ given​ for <em>orienting</em>​ the​ robot​ on its 0° axis within an error tolerance of <strong>±10</strong>​ <strong>°</strong>​. A penalty of <strong>5</strong>​<strong> points per ±10° </strong>is​ used for angles beyond 10°. Hence, the following points are awarded for the actual robot’s orientation:</li>

 <li><strong>± [0, 10] °</strong> → <strong>5 points</strong></li>

 <li><strong>± (10, 20] ° </strong>→ <strong>5 points</strong></li>

 <li><strong>± (20, </strong><strong>∞</strong>​ <strong>)</strong>​<strong> ° </strong>→ <strong>0 points</strong></li>

</ul>

<h3>Ultrasonic Localization</h3>

<ul>

 <li><strong>5 points </strong>are​ given​ for orienting​ the​ robot​ along its 0° axis at point (1, 1) within an error tolerance of <strong>±5</strong>​ <strong>°</strong>.​ A penalty of <strong>5</strong>​<strong> points per 5° </strong>​is used for angles beyond 5°. Hence, the following points are awarded for the actual robot’s orientation:</li>

 <li><strong>± [0, 5] °</strong>     →        <strong>5 points</strong></li>

 <li><strong>± (5, 10] ° </strong>→        <strong>5 points</strong></li>

 <li><strong>± (10, ∞) ° </strong>→        <strong>0 points </strong></li>

</ul>

<strong> </strong>

<ul>

 <li><strong>10 points </strong>are​ given​ for reaching​ point (1, 1) within an error tolerance of <strong>3</strong>​<strong> cm</strong> using a <em>Euclidean distance</em>​. A penalty of <strong>5</strong>​<strong> points per 3 cm</strong> is​ used for distances beyond 3 cm. Hence, the following points are awarded for the actual robot’s position relative to the point (1, 1):</li>

</ul>

<table width="260">

 <tbody>

  <tr>

   <td width="47">●</td>

   <td width="97"><strong>[0, 3] cm</strong></td>

   <td width="48">→</td>

   <td width="68"><strong>10 points</strong></td>

  </tr>

  <tr>

   <td width="47">●</td>

   <td width="97"><strong>(3  6] cm</strong></td>

   <td width="48">→</td>

   <td width="68"><strong>5 points</strong></td>

  </tr>

  <tr>

   <td width="47">●</td>

   <td width="97"><strong>(6, 9] cm</strong></td>

   <td width="48">→</td>

   <td width="68"><strong>2.5 point</strong></td>

  </tr>

  <tr>

   <td width="47">● </td>

   <td width="97"><strong>(9, ∞) cm</strong></td>

   <td width="48">→</td>

   <td width="68"><strong>0 points </strong></td>

  </tr>

 </tbody>

</table>

<ul>

 <li><strong>BONUS: Light Localization – </strong>are​ given​ for reaching​ point (1, 1) within an error tolerance of <strong>2</strong>​<strong> cm</strong> using a <em>Euclidean</em>​<em> distance</em>​. A penalty of <strong>5</strong>​<strong> points per 2 cm</strong> is​ used for distances beyond 2 cm. Hence, the following points are awarded for the actual robot’s position relative to the point (1, 1):</li>

</ul>




<table width="237">

 <tbody>

  <tr>

   <td width="24">●</td>

   <td width="97"><strong>[0, 2] cm</strong></td>

   <td width="48">→</td>

   <td width="68"><strong>10 points</strong></td>

  </tr>

  <tr>

   <td width="24">●</td>

   <td width="97"><strong>(2, 4] cm</strong></td>

   <td width="48">→</td>

   <td width="68"><strong>5 points</strong></td>

  </tr>

  <tr>

   <td width="24">●</td>

   <td width="97"><strong>(4, 6] cm</strong></td>

   <td width="48">→</td>

   <td width="68"><strong>2.5 point</strong></td>

  </tr>

  <tr>

   <td width="24">●</td>

   <td width="97"><strong>(6, ∞) cm</strong></td>

   <td width="48">→</td>

   <td width="68"><strong>0 points</strong></td>

  </tr>

 </tbody>

</table>

<h1>Provided materials</h1>

<h2>Sample code</h2>

No sample code is provided for this lab. Instead follow the guidelines given below:

<ul>

 <li>Create a UltrasonicLocalizer​ class that performs the ultrasonic localization routine.​</li>

</ul>




<ul>

 <li>Optional: Create a LightLocalizer​ class that performs the light localization routine.​</li>

</ul>

<h1>Implementation instructions</h1>

<ol>

 <li>Using the class definitions above, implement the ultrasonic localization versions.

  <ol>

   <li>For more information see the tutorial provided.</li>

  </ol></li>

 <li>Using the class definition above, implement the localization routine(s).</li>

 <li>Create a main class that:

  <ol>

   <li>First, corrects the angle of the robot and then waits for input by the user before moving to the grid intersection.</li>

   <li>Second (if you choose to do the bonus), your robot must pause after the angle localization and wait for user input before continuing to light localization.</li>

  </ol></li>

</ol>




<h1>Report Requirements</h1>

The following sections must be included in your report. Answer all questions in the lab report and copy them into your report. For more information, refer to

<u>ECSE211SubmissionInstructions.pdf</u>.<u>​</u> <strong>Always</strong>​<strong> provide justifications and explanations for all your answers</strong>.​

<h2>Section 1: Design Evaluation</h2>

You should concisely explain the overall design of your software and hardware. You must present your workflow, an overview of the hardware design, and an overview of the software functionality. You must briefly talk about your design choices before arriving at your final design. Visualizing hardware and software with graphics (i.e. flowcharts, class diagrams) must be shown.

<h2>Section 2: Test Data</h2>

This section describes what data must be collected to evaluate your design requirements. Collect the data using the methodology described below and present it in your report.

<strong>Test localization </strong>(​ <em>10</em>​ <em> independent trials</em>​)

<ol>

 <li>Place the robot in a tile corner along the 45° line (<strong>Figure 1</strong>​ )​ , where two walls are present.</li>

 <li>Choose a random orientation for the robot.</li>

 <li>Run the ultrasonic localization routine.</li>

 <li>Note the ultrasonic angle of the robot.</li>

 <li>Compute the ultrasonic angle error using the ultrasonic angle and the expected value.</li>

 <li>Continue the localization using the ultrasonic sensor to center at (1, 1) and 0°.</li>

 <li>Note the final position and final angle of the robot.</li>

 <li>Compute the Euclidean distance error​ and final angle error.​</li>

 <li>Report in a table: ultrasonic angle error, Euclidean distance error​ , and final angle error.​</li>

</ol>

<h2>Section 3: Test Analysis</h2>

For each test, compute the mean and standard deviation of the ultrasonic angle error, Euclidean​      distance error, and final angle error. Be sure to show general formulas and sample calculations.​

<h2>Section 4: Observations and Conclusions</h2>

<ol>

 <li>Describe other possible localization techniques and explain why you chose yours.</li>

 <li>Was the final angle impacted by the initial ultrasonic angle?</li>

 <li>What factors do you think contributed (positively and negatively) to the performance of your method?</li>

 <li>Do you think that the ultrasonic sensor or the light sensor method performs better? (If you did not do the bonus answer based on the reliability/quality of the readings of the light sensor vs. ultrasonic sensor). In future labs which one do you plan to use for navigating?</li>

</ol>

<h2>Section 5: Further Improvements</h2>

<ol>

 <li>Propose a software or hardware way to minimize errors in the ultrasonic sensor.</li>

 <li>Propose another form of localization.</li>

 <li>Discuss how and when light localization could be used outside of the corner to correct Odometry errors, e.g. having navigated to the middle of a larger floor.</li>

 <li>How could the robot quickly localize given two light sensors?</li>

</ol>