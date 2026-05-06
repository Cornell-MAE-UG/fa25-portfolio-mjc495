---
layout: project
title: Functional Prototype
toc: True
---

---

<p style="text-align:Center;">
</p>
<p style="text-align:Center;">
  <img src="{{ '/assets/images/FirstPrototype.png' | relative_url }}"
       alt="Prototype Sketch"
       style="width: 300px; height: auto;">
</p>
Assembly

1. Fit 2 cm of hose into the cyclone and apply hot glue around the edges of the cyclone to secure the two together and provide an air-tight seal

2. Assemble the aperture according to the design manual

3. Screw the aperture on the end of the nozzle

4. Glue the other end of the nozzle into the cyclone inlet

5. Create a stand using wooden beams
a. Use three wood planks to make a U shape. The horizontal plank is 14 inches wide to match the width of a standard conveyor belt.
b. Glue the vertical beams to the horizontal base and side of cyclone
c. Attach clamps to the horizontal base

6. Attach the collection bag to the outlet of the cyclone with glue/tape

7. Clamp base to the side of the conveyor belt

<p style="text-align:Center;">
</p>
<p style="text-align:Center;">
  <img src="{{ '/assets/images/PrototypeSketch.png' | relative_url }}"
       alt="Prototype Sketch"
       style="width: 300px; height: auto;">
</p>
<p style="text-align:Center;">
</p>
<p style="text-align:Center;">
  <img src="{{ '/assets/images/Aperture.png' | relative_url }}"
       alt="Prototype Sketch"
       style="width: 300px; height: auto;">
</p>
The Aperture (shown above) consists of eleven leaves that are laid out and clamped to the base using pins and screws, each leaf having one degree of motion.

---

## Design Tests

### Test 1: What is the maximum distance and aperture diameter above the conveyor belt such that it can suck up 2-3 grams?
Method of testing: Using a 3g target object weighed on a scale, lower the vacuum closer to the target slowly until the target gets sucked up. The height at which the vacuum picks up the target is recorded using a ruler, and this is the height relative to the table. The height relative to the target is also recorded by subtracting the target height from the height above table. This allows us to see how far the vacuum must be from the top of the object that we want to pick up. We will test this with a few different aperture diameters to see how adjusting the aperture impacts the vacuum’s lifting power. This is testing for the max height at which we can place the aperture above the conveyor belt. It is also testing to see if the vacuum can suck up SLFs when the aperture is set to different diameters. 

Test Results:
<p style="text-align:Center;">
</p>
<p style="text-align:Center;">
  <img src="{{ '/assets/images/Test1Results.png' | relative_url }}"
       alt="Prototype Sketch"
       style="width: 500px; height: auto;">
</p>

Conclusion:
For this test, we had to use a weaker vacuum than the one we selected for our prototype since it had not been delivered yet. As expected, we noticed that a wider aperture correlated with a significant reduction in pickup height relative to the target. Overall, we witnessed that this weaker vacuum did not allow us to get as much height above the target or as wide an aperture diameter as we were aiming for. For the next iteration, we will have to do this test again using the more powerful vacuum and see if it makes a significant difference in comparison to these results. If we are still not able to get the aperture to be at least 3-4cm above the target and reliably pick it up, we may have to adjust our expectations for the diameter of the aperture or make design changes to our nozzle structure that allow us to get more suction out of our vacuum.

---

### Test 2: General Reliability

Method of testing: run the system for 10-15 minutes to see if anything fails. Shake the structure with light to medium intensity to see if it is structurally secure against bumps. This is testing the overall structure of the system, such as the vacuum, nozzle, and supports. This is testing for which part, if any, will fail when the system is running for an extended period of time.

Test results: 
The support structure for our nozzle stayed secure for 10 minutes of the vacuum running, with the aperture remaining parallel to the conveyor belt(flat sheet on the table) for the whole duration. The structure held up against simulated bumps and was overall very structurally sound.



Conclusion for next iteration:
Our current structural support for the nozzle is stable and is a good basis for future iterations. Since there is currently no reason to change this based on our results, we will repeat the same support structure for our second iteration. We will have to do another reliability test when our vacuum arrives to make sure it runs for an extended time.

---

### Test 3: Cyclone Test

Method of testing: Suck up a 1g target object and see if it reliably falls into the collection bag instead of being sucked up. Repeat this test 10 times, and record the number of successes and failures. The goal is for at least 75% of the lanternflies to end up in the bag. This is testing to see if the cyclone will effectively funnel SLFs into the collection bag, or if they will be sucked into the vacuum.

Test results:
Trials: 10
Successes (model SLF in collection bag*): 9
Failures(model SLF sucked into vacuum): 1

Conclusion for next iteration:
The cyclone is effective and passes our goal of a 75% success rate. We will have to repeat the test when our Amazon vacuum comes in for our second iteration, but for now, it seems that there are no design changes necessary to the cyclone.
*While the cyclone itself was effective in preventing objects from being sucked into the vacuum, we noticed that the collection bag was made ineffective due to vacuum suction, so instead of falling into the bag, objects would stay in the cyclone endlessly. In future iterations, we will keep the cyclone the same, but replace the bag with a rigid container to fix the collection process.

---

## Success Criteria

To address the spotted lanternflies that exist in the final stage of collection before entering collection bins, we want our final prototype to be able to suck up objects with a maximum mass of 3 grams (average SLF mass) but not 5 grams (average grape mass). This is assessing the suction power of our system to ensure that spotted lanternflies are consistently removed from the conveyor belt before bin collection, and we are measuring the suction power by using test objects that have varying masses (1 to 5 gram objects) to see which masses are successfully sucked up, given the same aperture diameter of 2cm; during exhibit-day, our success is determined by our ability to suck up mock flies 95% of the time and leaving 95% of all mock grapes.


