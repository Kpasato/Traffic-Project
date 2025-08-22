## CSE241 Midpoint
## NOTE: For final Submission portion skim until you find:CSE Final Submission portion below


A problem explanation that describes in words what you are actually designing based on all the facts provided to you.




## Problem Explanation: 
In this problem we have two roads, a country road and a highway road that intersect eachother. The roads are perpindecular to eachother and both only go one way. Since both roads only go one way, there will only be one light that is either red or green on each road. What we have are multiple different possible cases/states possible for different situations given. The possible states will be based on a sensor enable, a vehicle counting sensor, and a weather sensor.


## Problem Explanation Inputs/Outputs:
The 2 inputs for this problem will be the vehicle counting sensor and the weather sensor. The 2 outputs of this problem are the highway road light and the country road light.

**Problem Explanation:**
The goal is to make sure that our roads are going to have a safe system that has a state and next state for all the possible inputs given. This would mean that the lights will be changing continuosly and not end up having an instance where both lights stop and no changes happen.


## State Diagram:
<img width="817" alt="Screen Shot 2022-05-06 at 11 55 56 PM" src="https://user-images.githubusercontent.com/90589157/167237263-fb3474f6-3da6-439b-bc76-c9ab81211313.png">
<img width="786" alt="Screen Shot 2022-05-06 at 11 55 52 PM" src="https://user-images.githubusercontent.com/90589157/167237269-e1d62191-47db-4679-b7b6-e17faded000a.png">
<img width="764" alt="Screen Shot 2022-05-06 at 11 55 37 PM" src="https://user-images.githubusercontent.com/90589157/167237271-f2333b93-f142-40f1-880f-ac9c8c40f49a.png">
<img width="752" alt="Screen Shot 2022-05-06 at 11 55 24 PM" src="https://user-images.githubusercontent.com/90589157/167237276-ccc5c389-6522-4e6d-9ada-f96852a45542.png">



## Explanation Of Considerations:
**-** Both lights can be red at once when changing colors to avoid collisions but both can't be green
**- Highway Road Light:** This will be 1 when on and 0 when off.
**Country Road Light:** This will be 1 when on and 0 when off.

**- Vehicle counting sensor:** 
The vehicle counting sensor changes after a car crosses the intersection, this sensor only counts up to 1 and after it is 1 it changes back to 0. When this sensor is 1 it changes the light of both roads to make the country light green and the highway light red, the opposite for when it is 0. While it changes colors for both roads there will be a short time when both roads are red. When this sensor is off the country road light will be set to 0/red light while the highway road will be 1/green light(this is because when the vehicle sensor input is 0 the highway light is green).

**- Weather sensor:**
This sensor tells us if it is snowing or not. If it is snowing it will be 1 and when it is not snowing it is 0. If it is 1 it will turn the enable sensor off.

**- Sensor enable:**
This will always be on/1 unless the weather sensor tells it that it is snowing. If this is off/0 then the vehicle counting senor is also off/0.
Since the weather sensor tells us when to turn this on or off we will not consider this an input.


## Explanation of reasoning in design: 
The reasoning behind making this design was based off the possible changes that could occurr when the counting sensor changes and the weather sensor changes. It shows how it changes when the weather sensor doesnt turn on and when it does turn on and how it impacts the country road light and the counting sensor.


------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## **CSE Final Submission portion below**
REPO LINK: https://github.com/cse241-SP22/final-project-Kpasato.git


**Introduction:**
In this report we will explain a design problem based off two roads that intersect and show the steps taken to design a control system from the design problem. This control system will output based off its current situation(state) and the inputs.
The aim of this design problem is to have a system that is able to have multiple different outcomes for each of the possible scenarios(states) for both road lights.
**Specifications:**

● Two roads intersect perpendicularly. 

● One road is a highway road. 

● One road is a country road. 

● There is a traffic signal for each road. 

● Traffic only runs in one direction on each road. 

● There are no delays from external factors in this system, so it doesn’t matter if the sun is visible. 

● There is a bridge further down the highway. 

● Each signal can be green or red. (Yeah in reality there is yellow, but that makes this problem harder) 

● Both signals can not be green at the same time, but there are times when both should be red. 

● Cars and trucks use these roads. So do motorcycles.

● It doesn’t matter how many people are in the vehicle. 

● A vehicle is anything with wheels. 

● There is an overall enable that corresponds to the sensor counting the vehicles being on or off; if the sensor is off, then the country road will have a red light. 

● The vehicle counting sensor will always enabled on unless it is snowing. ● If you follow the country road you will find a pumpkin farm. 

● There is a weather sensor that tells if it is snowing or not. 

● There are three vehicles parked on the side of the road 

● There is a counting sensor that tells how many vehicles pass through the intersection. 

● All vehicles are treated equally independent of how many wheels it has. 

● The counting sensor, weather sensor, and the sensor enable must be used as a factor to decide which color each signal is. 

● Each time you have to change the signal color, you must temporarily have both signals red to avoid collisions. 

● During the transition time for the signal, there will be no vehicles going through the light, so the counting sensor can be ignored. (You can assume ideal behaviors of the drivers) 

● The area has lots of wild turkeys roaming around and the occasional goose. 

● Vehicles move at a constant speed. 

● You can assume that the speed of the vehicles, calculation time and clock period are ideal and don’t have to be considered beyond a basic delay in the test bench to verify the logic.

**Design Problem:**
In this problem we have two roads, a country road and a highway road that intersect eachother. The roads are perpindecular to eachother and both only go one way. Since both roads only go one way, there will only be one light that is either red or green on each road. Both lights can be red at once but both cannot be green at once. The lights for both roads are based off 4 components which are: a weather sensor, a counting, a sensor enable, and the current situation(state) that the intersection is in.
Below are explanations for the 3 sensors.

**Counting Sensor:**
The counting sensor tells us how many vehicles cross the intersection and changes after a car crosses the intersection, this sensor only counts up to 1 and after it is 1 it changes back to 0. When this sensor is 1 it changes the light of both roads to make either the country road light green/red or highway road light green/red. While it changes colors for both roads there will be a short time when both roads are red, this is to avoid collisions. When the counting sensor is 0 it will stay on the current situation(state) that the intersection is in.

**Weather Sensor:**
This sensor will tell us if it is snowing or not. If it is snowing it will make the inputs of the counting sensor irrelavent to the output. The country road light will also be red when it is snowing and the highway road light will be green.
Sensor Enable: The sensor enable is always on unless it is snowing. If it is off it will also turn off the counting sensor and turn the country road light red. Since the weather sensor itself does this by making the counting sensors inputs irrelavent to the output and turning the country road light red when it is on, we will not need to use a sensor enable.(The point in including this is to explain why the use of 2 inputs instead of 3 was able to occur)


**Background concepts:**
- sequential logc
- Deciphering datasheets
- combinational logic
- state diagram creation


**Documentation of the design approach and the design solution:**

KEY:
ws = weather sensor

cs = counting sensor

hr = highway road light

cr = country road light

g = green light / 1

r = red light /  0 

Q1 = first bit of the state in transition table

Q2 = second bit of the state in transition table

Q1* = function for first bit in transition table

Q2 = function for second bit in transition table

**State Assignments:**
00 = State A in transition table

01 = State B in transition table

10 = State C in transition table

11 = State D in transition table

The approach taken for this design was to first figure out the possible situations(states) that could happen to change the lights on the road. Making the state diagram below made finding out the possible states easy to figure out. After making the state diagram I made a state table which then helped me make a transition table based on the state table and with the transition table I made the transition equations and output equations. With the equations I then made the schematic to build the system.


**Description of the state diagram itself:**
In the state diagram I will explain how it works when starting on state A, so state A is when the weather sensor is on. So every state goes back to state A once weather sensor is on(ws=1). When ws = 1  if the cs=1 or 0 it doesnt change the state its in.
Once ws = 0 it will stay on state A until cs = 1. Once cs = 1 it will transition through the states and if it turns to 0 during state A or C it will stay on those states. States B and D are just transitions states from state A to C or C to A, so they are the instances when both lights are red. 
The reason I need two states for this is because the transition that occurs in state D happens when the cs = 1, and if the state that we were in was on state C and the ws=1 then state D couldn’t occur since when ws=1 the cs input does not effect the state it will go to. So essentially the transition that occurs from state D is when ws=0 and state B is when ws = 1.
Note:
 In state A, hr = 1(green) and cr=0(red). While when in state C cr =1(green). 

**State Diagram:(ps: I ended up remaking my state diagram from my midpoint submission so it’s different)**


<img width="663" alt="Screen Shot 2022-05-18 at 3 17 10 AM" src="https://user-images.githubusercontent.com/90589157/169187127-bf11ea41-7bc5-411c-8e97-220a482f7a41.png">


**State Table:**

<img width="663" alt="Screen Shot 2022-05-18 at 3 17 10 AM" src="https://user-images.githubusercontent.com/90589157/169187166-ee4ef117-f9e7-49a8-afcc-88d485d578ad.png">


**Transition Table:**

<img width="710" alt="Screen Shot 2022-05-18 at 3 25 39 AM" src="https://user-images.githubusercontent.com/90589157/169187278-beee62d6-bdf2-460f-908c-702db9f37078.png">

**Transition Equations:**

<img width="566" alt="Screen Shot 2022-05-18 at 3 26 42 AM" src="https://user-images.githubusercontent.com/90589157/169187352-4616f4ee-9359-4dcc-9792-90e493f8f710.png">

<img width="567" alt="Screen Shot 2022-05-18 at 3 26 54 AM" src="https://user-images.githubusercontent.com/90589157/169187361-14588392-cd8f-4971-ae06-8a0a2e13f560.png">

**Output Equations:**

<img width="705" alt="Screen Shot 2022-05-18 at 3 27 03 AM" src="https://user-images.githubusercontent.com/90589157/169187385-8d9a10ad-6f5b-432f-a46a-ac87baf6606f.png">

**Schematic:**

<img width="738" alt="Screen Shot 2022-05-18 at 9 45 35 PM" src="https://user-images.githubusercontent.com/90589157/169187433-596eaa81-e7de-4a2e-b4bf-ad34378702ef.png">

**Tools and Resources**
Bill of materials:
49 Jumper wires
4 Standard LEDs - Through Hole 5mm Round
3 AND gate IC’s -xx74xx08xx
1 OR gate IC -xx74xx32xx
1 Not gate IC -xx74xx04xx
1  Logic D-Type F-F w/Reset IC -xx74xx175xx
4 Carbon film resistors
1 Full sized solderless breaboard

Software: Function generator and function writer
Equipment: National instruments NI mydaq

**Documentation describing physical construction and testing of implementationg:**
**Reminder:**
WS = weather sensor
CS = counting sensor
HR = Highway road light
CR = Country road light
Physical construction:
Step 1: Gathering the bill of materials
Step 2: Place 2 led lights that represent the inputs weather sensor and counting sensor on the breadboard. Ground the led’s and place carbon film resistors in the middle of the rows on the breadboard
Step 3: Place the following IC’s on the breadboard in the following order: NOT,AND,OR,D-type flipflop(-xx74xx175xx), AND, AND. Ground the IC’s and connect them to power. 
Step 4: Place 2 more led lights on the end of the breadboard. Ground the led and place carbon resistors in the middle part of the row that the led’s positive end is in.
Step 5: Have a wire connect the weather sensor and NOT gate together and have the output of that wire go to an AND gate input. Then have a wire connect Q1’ from the D-type flip flop IC to the other input in the AND gate. With the output of these 2 wires AND’d together, have it connect to another pin in the AND gate its in. Then have another wire connect from the D-type flip flop IC’s Q2 pin to the other AND gate input so that WS’Q1’Q2 would be the output from that AND gate. With this output connect it to an OR IC’s input.
Step 6: Connect a wire next to our previous(step 5) output of ws’ and connect it to an AND gate input, then have a wire connect from Q1 to the other input of the AND gate. With the output of the two inputs have it connect to an input for an AND gate, then have Q2’ connect to the second input.The output of the AND gate(WS’Q1Q2’) will then be connected to the second input of the OR gate that we used in step 5. The output of the two OR’d together(WS’Q1’Q2+WS’Q1Q2’) will then be connected to the D1 pin of the D-type flip flop IC.
Step 7: Now that we have filled up an AND IC, we will use another AND IC. Connect the input WS to an input of the AND gate, then connect Q1 to the other AND input. Have the output of the AND gate go into a pin for another AND gate, then connect Q2’ to the second input in the AND gate and have the output(WSQ1Q2’) of this AND gate go to an input in the OR IC.
Step 8: We will now connect WS’ to an input of an AND gate in our second AND gate IC, then connect CS to the second input. Now have the output of this go to an input of another AND gate, then have a connection from Q2’ to the second input. With the output(WS’CSQ2’) connect it to the second input for the OR gate from step 7. With the output of the two OR’d together(WS’CSQ2’+WSQ1Q2’) connect it to D2 in the D-type flip flop. 
Step 9: Connect Q1’ to an AND gate in our third AND IC, then have Q2’ connected to the second input of the AND gate and have the output go to one of the LED lights at the end of the breadboard. (This LED will be the output for HR)
Step 10: Connect Q1 to and And gate in our third AND IC, then have Q2’ connected to the second input of the AND gate and have the output go to the last LED that isn’t connected to an input. (This LED will be the output for CR)

**Testing:**
For testing this system I will start at State A by turning on the weather sensor. 
Test Case 1: When at state A we will change the counting sensor to 1 and 0 over and over to see if the output changes.The output should be that Highway road is green and Country road is red. This tests to see if counting sensor impacts the output when weather sensor is on which it shouldn’t.
Test Case 2: We will change ws to 0 and then back to 1 while in state A. What should occur is that when ws changes while in state A, the state will remain in A. So the outputs should still be CR = 0 and HR = 1. This tests to see if the ws impacts State A when it is already in State A.
Test Case 3: While in State A we will set ws to 0 and cs to 1 and what should occur is that the state changes from A to B. In this state B, the outputs of HR and CR are 0. So this tests to see how when cs is 1 it impacts state A when WS=0 as well.
Test Case 4: While in State B we will change WS to 1 and see if it goes back to state A. This tests to see is WS makes the state go back to A which it should. HR should turn 1 and CR turn 0. 
Test Case 5: While in State B we will keep ws to 0 and change cs to 0 as well. Since State B is a transition state we will test to see if cs being turned to 0 makes the state be stuck on state b which it shouldn’t. What should happen in this situation is that B transitions to State C and the outputs are HR=0  and CR=1.
Test Case 6: While in state C we will change ws to 1 and see if the state changes to state B and then back to state A. This will show us that weather sensor impacts state C.
Test Case 7: We Will turn the counting sensor to 0 while in state C and see if the state changes. What should happen is that when cs=0 on either state A or C, it will stay on that state as long as WS is also 0. The outputs should be CR=1 and HR =0.
Test Case 8:
Since state B and D are similar in that both lights are 0(red) when it is on that state, we will now check to see how they differentiate. By turning cs to 1 and ws to 0 while in state C and then changing ws to 0 as both lights are red, we will see if the output will become the output of state A or C. What should occur is that we should be in state A because ws doesn’t impact state D. Hr should be 1(green) while CR = 0(red).

**Testing with System verilog:**
The way you would test in system verilog is to test multiple different states with all the possible inputs. So in our system we would have 4 different states and all possible inputs are 4 so you would need to test 16 possible cases and see if based on the state and the inputs, the correct output is shown.

**SystemVerilog Code:**

[resultCSE241SV.zip](https://github.com/cse241-SP22/final-project-Kpasato/files/8723210/resultCSE241SV.zip)


**Analysis Plan:** If I was given video recordings of the intersection, a log file of the inputs/outputs, and a waveform of the inputs/outputs, the way I would approach verifying the design would be to first figure out what state the intersection was in. I would do this by first using the waveform to figure out what signals are on of off for the weather sensor and counting sensor. The reason I would use the waveform is because since there can be multiple different cases where the inputs are different and the outputs are the same, it will avoid issues when just basing off what the state is from the lights in the video recording and the log file. Once I figure out which state it is I would check the log file and see what the lights for both roads should be based off the state and inputs. Once I know what the outputs should be based off the inputs and state, I would check one of the video recordings and see if the outputs are correct. I would then do this for all the other recordings  to verify that all situations for the given inputs/outputs are correct.

**Conclusion:** When working with this design problem I was able to construct a simple traffic system that is able to be used in a situation where roads intersect each other, go one way, are dependent on 2 factors, the lights on the both roads are either green or red, and the both lights can be red at once but not green at once. Some of the  outcomes that came from working on this project where that I was able to understand sequential logic more, figured out how to work with D-flip better, was able to decipher a way of working with the design problem, and became more familiar with working with state diagrams, state tables, transition tables, transition equations, and output equations. 

**Future Recommendations:** 
- I feel as though the use of the github was unecessary and would have much rather preferred just sending a pdf to submit instead.
- I think that the timing of this project was off, I do not think It should have been due during finals week and it should have been given earlier for more time.
- Although I received full credit for the demo, I think that the grading gap was very steep in it and it should be somewhat more reasonable to receive partial credit
- I think having more examples/resources to figure out how to make a testbench for a sequential circuit would have been useful
**References and resources:**
- Sv testbench demos 
- April 15th to May 7th Lecture notes
- Lecture recordings of Sv demos
This project was designed and implemented by Kevin Pasato in Spring 2022 for CSE241 at the University at Buffalo. Content in this repository is not to be reproduced or utilized without written authorization from the instructor, Dr. Winikus (jwinikus@buffalo.edu). 







