---
title: Curtain Breaks
type: docs
---

# Curtain Breaks

Project documentation for the Design for **Physical Prototyping** course 2023/24 focusing on the topic of **Chindōgu**

## Team

- Jungmann Leo
- Rodler Hanna
- Romelli Elena

## Abstract

Curtain Breaks is helping people take breaks from sitting too long at a time. By rolling down a curtain after a certain time, the laptop screen is hidden. The user then needs to leave the space in front of the laptop for at least one minute for the curtain to roll back up again.

## <a id="Introduction"></a>Introduction

People usually spend too much time sitting down at the desk. They take too little breaks to stand up, walk a few steps and get a fresh mind. The Chindogu Curtain Breaks helps people take these breaks.
{{< figure src="assets/CurtainBreaks1.png" caption="*Sketch of the originally planned Curtain Breaks.*">}}
When the user sits down, they can set a time on a LED Display using a rotary button (originally an "up" and "down" button) that will determine how many minutes they can remain sitting. The maximum that they can stay seated is 60 minutes. The LED Display is mounted on the top of the laptop screen along with the buttons. Next to the LED Display, there is a proximity sensor that senses if the user is sitting in front of the screen.
Above these sensors there is a bar mounted to the screen with a fabric rolled around it.
{{< figure src="assets/Curtainbreaks2.png" caption="*Curtain Breaks from the front showing the LED Display, the buttons, the proximity sensor and the curtain mounted on top.*">}}
{{< figure src="assets/CurtainBreaks3.png" caption="*Curtain Breaks from the back still showing an originally planned battery and on/off button.*">}}
{{< figure src="assets/CurtainBreaks4.png" caption="*Curtain Breaks from the side.*">}}

When the user is not standing up after the set time, the proximity sensor will sense it and the curtain will start to be rolled down in front of the laptop screen.
{{< figure src="assets/CurtainBreaks5.png" caption="*Sketch of the curtain being rolled down in front of the laptop.*">}}

The curtain will only roll back up if the user is gone at least one minute. This is again sensed by the proximity sensor.

Here's a video of the final prototype, demonstrating how CurtainBreaks works:

<video autoplay="true" loop="true" muted="true"> <source src="assets/Final.mp4" type="video/mp4"></video>

**How does the user interact with the device and what action does it perform?**

As described above, the user interacts with the device via two buttons for setting the minutes and by simply sitting in front of it. The latter will be sensed by the proximity sensor. When the user does not go away after the set time has passed, the device will react to it.

**Where, when and by whom would the device be used?**

Curtain Breaks would be used by everyone struggling to take breaks or too comfortable sitting down while working on a laptop, not realising the benefit that standing up can have. It would mostly be used on the laptop at home or at work, somewhere where the laptop is used for a longer time.

**How does the device relate to the concept of Chindōgu?**

Regarding the Ten Tenets of Chindōgu, our device fulfils Tenet one and two as it could almost actually be used but is unlikely to really be used due to the complexity and impracticality yet fun and original idea of the Curtain going down over the laptop. It also supports freedom of thought and action and is not bound to capitalist measures like that everything that is created needs to be useful and sellable (Tenet 3). Additionally, it can be non-verbally understood by people all over the world and doesn‘t favor anyone (Tenet 4 and 10) as our Chindōgu just requires only the time to be set and people to sit in front of it. Furthermore, Curtain Breaks tries to solve the problem of people sitting to much in an innocent way and with best intentions at heart as well as being socially decent (Tenet 6, 7 and 8). It is just created to be created and train and support our abilities as creative – quite literally creating – humans and will not be sold or patented (Tenet 5 and 9).

## Related work

**About prolonged sitting and taking breaks:**

- _Chau, J.Y., Daley, M., Dunn, S. et al. The effectiveness of sit-stand workstations for changing office workers’ sitting time: results from the Stand@Work randomized controlled trial pilot. Int J Behav Nutr Phys Act 11, 127 (2014)._ https://doi.org/10.1186/s12966-014-0127-7
  It has been shown that sitting for extended periods has negative health implications, particularly for those with office jobs who tend to sit for long hours. To mitigate this, sit-stand workstations have been considered a viable solution to reduce prolonged sitting. This paper aims to investigate how the use of sit-stand workstations impacts the sitting time of office workers both during their work hours and throughout the entire day. The researchers conducted a randomized controlled trial pilot called Stand@Work to assess the effectiveness of sit-stand workstations in reducing sedentary behavior in the office.
  The findings revealed that, compared to the control group, the participants in the sit-stand workstation group experienced a significant reduction in sitting time during work hours. They also reported lower levels of overall sitting time during a typical workday. The sit-stand workstation group showed improved perceptions of health and well-being.

- _Mantzari E, Galloway C, Wijndaele K, Brage S, Griffin SJ, Marteau TM. Impact of sit-stand desks at work on energy expenditure, sitting time and cardio-metabolic risk factors: Multiphase feasibility study with randomised controlled component. Prev Med Rep. 2018 Nov 26;13:64-72. doi: 10.1016/j.pmedr.2018.11.012. PMID: 31304079; PMCID: PMC6603239._
  As for the previous study, this study, aims to investigate the effects of sit-stand desks in the workplace on energy expenditure, sitting time, and cardio-metabolic risk factors. The research was conducted as a multiphase study, consisting of a feasibility phase (surveys and interviews) followed by a randomized controlled trial (RCT) component.
  This suggests that the introduction of sit-stand desks in the workplace can effectively reduce sitting time, increase energy expenditure, and lead to positive changes in cardio-metabolic risk factors. These findings highlight the potential of sit-stand desks as an intervention to promote a more active and healthier work environment.

The insights from these two papers on sit-stand workstations align with our project's goal of combating excessive desk sitting. We aim to prompt users, in a fun way, to stand up and take breaks from prolonged sitting. The papers suggests that ergonomic solutions can effectively reduce sitting time, much like our Chindogu's approach using a proximity sensor to encourage breaks and healthier habits.

**About solution to limit time seated on screens:**

- _Benjamin Gardner, Lee Smith, Fabiana Lorencatto, Mark Hamer & Stuart JH Biddle (2016) How to reduce sitting time? A review of behaviour change strategies used in sedentary behaviour reduction interventions among adults, Health Psychology Review, 10:1, 89-112, DOI: 10.1080/17437199.2015.1082146_

  The paper provides an extensive analysis of various behavior change strategies employed in interventions aimed at reducing sedentary behavior among adults. The authors identify and categorize various behavior change techniques used in these interventions.
  The findings indicate that interventions targeting sedentary behavior reduction employ a range of behavior change techniques. These techniques can be categorized into several broad categories, including education and awareness, environmental restructuring, and self-monitoring. Education and awareness strategies often involve providing information about the health risks associated with prolonged sitting and raising awareness among individuals. Environmental restructuring encompasses changes in the physical environment, such as the introduction of standing desks or activity-friendly workplaces. Self-monitoring strategies encourage individuals to track their sedentary time and set specific goals to reduce it. Additionally, some interventions incorporate goal setting, problem-solving, and social support to enhance behavior change.

The paper suggests that a combination of behavior change techniques, including self-monitoring and environmental restructuring, can effectively reduce sitting time. Our Chindogu incorporates a proximity sensor and a timer to prompt users to take breaks and stand up, which aligns with the concept of self-monitoring and environmental changes.

**About proximity sensors and HCI:**

- _Heindl, C., Ikeda, M., Stübl, G., Pichler, A., & Scharinger, J. (2019). Enhanced Human-Machine Interaction by Combining Proximity Sensing with Global Perception. arXiv preprint arXiv:1910.02445._ https://arxiv.org/pdf/1910.02445.pdf
  The paper introduces a novel approach to enhance human-machine interaction by combining proximity sensing with global perception technologies. Proximity sensing detects user presence and movements, triggering machine responses. Global perception offers a broader context of the user's environment. The fusion of these technologies enables machines to provide more personalized and context-aware interactions.
  The paper discusses several aspects of this combined approach. First, it highlights the significance of proximity sensing in recognizing when a user is in close proximity to a device. This can trigger actions or responses from the machine, such as waking from sleep mode or adjusting its behavior based on the user's presence. Proximity sensing technology, which may involve infrared sensors, capacitive touch, or other methods, plays a vital role in making machines aware of their users.

The paper discusses the use of proximity sensors, which aligns with our project's aim to encourage users to take breaks from sitting at their desks. Indeed, we could use the proximity sensor technology to detect when a user is sitting in front of their screen, initiating the break timer. Furthermore, the paper suggests that machines can adapt to users' needs. In our project, this means allowing users to set a specific time for staying sited. The paper's framework for personalization aligns with our Chindogu's goal of letting users determine the time according to their preferences.

**How to make automatic rollup curtain mechanism, some inspiration:**

- https://youtu.be/mG19jv71lpU?si=nfAWLBywUoTjdm_M
- https://youtu.be/kolGiMCPxlA?si=PFxuLW9j564wzMmZ
- https://youtu.be/B-6VDSFqSGM?si=6tha_c-aKN-oZeES

## Implementation

In the beginning we did some brainstorming and after bringing all of our ideas together, we first thought we could make sth that shoots pencils at the user when they don't take a break or an apparatus that starts to shake the laptop, so you cannot type anything anymore. But we thought we would maybe break something if we shake the laptop too hard and that the pencils could hurt. So we came up with a more peaceful way of encouraging the user to take a break: Curtains. These were our first sketches:
{{< figure src="assets/CurtainBreaks1.png" caption="*Sketch of the originally planned Curtain Breaks.*">}}
{{< figure src="assets/Curtainbreaks2.png" caption="*Curtain Breaks from the front showing the LED Display, the buttons, the proximity sensor and the curtain mounted on top.*">}}
{{< figure src="assets/CurtainBreaks3.png" caption="*Curtain Breaks from the back still showing an originally planned battery and on/off button.*">}}
{{< figure src="assets/CurtainBreaks4.png" caption="*Curtain Breaks from the side.*">}}
{{< figure src="assets/CurtainBreaks5.png" caption="*Sketch of the curtain being rolled down in front of the laptop.*">}}

We were planning to make the base on top of the screen out of wood, since it's rather lightweight when thin and can be crafted quite easily. For placing the controls we planned to cut out holes. To cut out the holes, we were able to use the CNC milling machine of Leo's father, which came in quite handy.

_We also planned the following:_ On top of the laptop, there is a rotatable bar that has a textile stripped to it. Combining that with a stepper motor, we are able to pull the textile down and back up again in front of the screen using an up and down button. A proximity sensor senses if the user is still in front of his computer. For the proximity sensor to work, the curtain has a hole cut out.

The timer is a LED display that can show 4 numbers. The first 2 digits are for the minutes and the other 2 are for the seconds. The user can set the timer in minutes up to a maximum of 60 minutes. The LED Display was exactly cut out, so it holds just by fitting tight into the hole.

All the sensors are connected to an Arduino Uno Board, which is connected to a battery supply and runs a program to control the sensors.
The program itself initially waits for inputs on the timer. When the timer is set, it counts down until it reaches zero. At that point, the stepper motor is is triggered to roll down the curtain. Then the proximity sensor consistently scans if the user is still sitting there. When the user is away for at least a minute, the curtain will roll up again and the program waits for another timer input.

We did not really have an entire iteration where we had to redo our whole prototype but we had some milestones where we realized we needed to change something in our plan.

### Iteration №1 - ProVotyping

In our ProVotyping session we figured out out, that we do not need a battery as originally planned and therefore also no power button. Instead we planned to mount the Arduino Uni Board on the back of the wooden construction and plug it in to the USB-Port of the laptop to provide power.
Furthermore at first we planned the parts mounted onto the laptop to have two sides.
{{< figure src="assets/PrototypeAbove.jpg" caption="*ProVotype from above*" width="75%">}}

But we figured out that for stability reasons it would be smarter to connect them.
{{< figure src="assets/PrototypeBackview.jpg" caption="*ProVotype from behind*" width="75%">}}

The two rolls on a stick on the side of the ProVotype symbolize where the roll with the curtain will be and where the curtain will be rolled up and down.
{{< figure src="assets/PrototypeRollCurtainDown.jpg" caption="*ProVotype - Roll Curtain Down*" width="75%">}}
{{< figure src="assets/PrototypeRollCurtainUp.jpg" caption="*ProVotype - Roll Curtain Up*" width="75%">}}

The ProVotype doesn't represent this accurately but from the beginning on we were planning to make the curtain the whole width of the laptop and cut out a part for the ultrasonic sensor.

In our final ProVotype the UltraSonic Sensor and the LED with the two buttons are also visible.
{{< figure src="assets/Prototype_FinalPrototype.jpg" caption="*Final ProVotype*" width="75%">}}

Since we had the same idea of how things would work out and look like, it was fairly easy to build our ProVotype. Building this and acting the scene out of what our Chindōgu would be used for was fun and helped us visualize our idea.

### Iteration №2 - Programming, Construction and realizations

While programming the sensors, we found out that it would be easier to use a rotary button instead of two buttons. It would have probably worked, but this was a better solution.

We had troubles to initially connect all of the sensors together so that the code would work for all of them, but we figured it out after a view tries. We also realized that it would after all be better to place the ultrasonic sensor fairly in the middle and not tilted on the side as we originally planned it in the ProVotype and our original sketches.
{{< figure src="assets/ProgrammingSensors.jpg" caption="*Programming the sensors*" width="75%">}}

We sketched out our wooden construction in Fusion. During that, we realized that we hadn't yet thought about how we would bring the cables to the back. So we redid the sketch to contain holes in the top part (lowest part in both of the sketches) to bring the cables back inside of the wooden construction and bring them back out at the back part to connect them to the Arduino Uno Board.
{{< figure src="assets/FusionSketch.png" caption="*Sketch of the Wooden Construction in Fusion*">}}
{{< figure src="assets/FusionSketch_Back.png" caption="*Sketch of the Wooden Construction in Fusion from the Back*">}}

When cutting the wood the fusion sketch needed to be changed a bit since the wood was thicker than originally planned and it was easier to change the measurements in the fusion file than cut the already somewhat thin wood thinner.
{{< figure src="assets/CuttingWood.jpg" caption="*Cutting the wood*" width="75%">}}

We assembled all of the parts together and then realized that for stability reasons another part on top that held the higher side parts together would be useful.
{{< figure src="assets/Assembling.jpg" caption="*Assembling the wood for the first time*" width="75%">}}
{{< figure src="assets/AssemblingStability.jpg" caption="*Adding a top bar for stability*">}}

**Soldering**: When planning how we would solder the cables to our board, we needed to redo our plan several times because we realized that the pins would stick out differently and that we all had different ideas of how to solder it. But we also figured that out and each of us had an input on what we could improve.
{{< figure src="assets/SolderingPlanning.jpg" caption="*Soldering Planning*">}}
Three weeks later after the christmas holidays we soldered. Two of us soldered and one of us was crimping the cables together. In the beginning we discussed which pins we should take and due to a miscommunication we took the wrong ones until we realized that the crimped and connected to the pins sensor wires wouldn't fit together with the board.

{{< figure src="assets/wrongPins.jpg" caption="*Having used the wrong pins*" width="50%">}}

We didn't managae to unsolder it so we created blobs to coonnect the pins on the back of the board.
{{< figure src="assets/pinsBlobs.jpg" caption="*Adding blobs to connect to correct pins*" width="50%">}}
{{< figure src="assets/pinsBlobsTop.jpg" caption="*The top of the board with the correct pins*" width="50%">}}

In the end we managed to set everything up correctly, though our miscommunication caused a mess on the board.
{{< figure src="assets/boardWithWires.jpg" caption="*The final board with the connected sensors*" width="50%">}}

**The Curtain:**
The lightest bit of fabric we had was a tiny bit see-through but due to the patterns of the fabric it was still sufficient enough to not in an way still see enough through the fabric to keep working.
{{< figure src="assets/Curtain.jpg" caption="*Curtain*">}}

This wasn't really a whole iteration or things that completely failed but things that we realised we could do better during the progress.

### Iteration №3

We mounted the sensors to the wood.
{{< figure src="assets/SensorsToWood.png" caption="*Mounting the sensors*">}}

{{< figure src="assets/WoodenConstruction.jpg" caption="*Wooden Construction for Laptop*">}}

Our final setup looked like this:

A detail description of our code can be found [here]({{< ref "SetupAndCode#Setup" >}}).

Leo's father helped us with some tips on how the stability of the wooden framework would be the best, as he is a hobby carpenter. So we implemented his ideas in the process, which were:

- We need that bar on the top for stability reasons (although the prototype gets heavier)
- How to screw the parts, by drilling small holes first (because glueing was not enough)
- How to use the CNC milling machine
- Crimping the cables instead of soldering them can be as good and is easier to do

We thank him very much for helping us with that.

After assembling all that, we only needed to connect the stepper motor and the bar with the curtain.
The stepper motor and the bar are connected on one side by shrinking tubes. On the other side, there is a ball bearing, so the bar can move smoothly. Connecting the stepper motor with a shrinking tube to the bar seemed to be working really good in the first place. However, minutes before the final presentation, we encountered problems with the motor stopping midst rolling down the curtain. We figured out, that this can be due to 1 of 3 problems:

1. The motor itself has problems, which we can only fix by replacing the motor
2. The connection with the shrinking tubes is not tight enough (which means the motor just turns inside the tube, without moving the bar)
3. Since the motor is not screwed or glued into its hole, it moves a bit when turning, due to that, it has loosen up the connection via the shrinking tube.

For the presentation, we just heated up the tubes again with a lighter and it worked. So we think it's a mix of problem 2 and 3. Looking back on that, it would have been better to use another method of connecting the motor and the bar. But, for a prototype it was good enough.

{{< figure src="assets/Prototype_Final_Presentation.jpeg" caption="*Prototype on the presentation day*">}}

This was our final prototype, that we used on the presentation day.
Despite all the challenges, the prototype reflected our initial ideas, and we were excited to share Curtain Breaks with the public!

## Conclusion

Making the prototype was a fun time with a few challenges. We really enjoyed it and it was great to have such a hands-on introduction to electronics.
We learned a lot about soldering and maybe we should have planned the final soldering more together again and not seperate the work, because then we would have probably realized our mistake with the pins sooner.
We were glad to get more time until January because there were also quite some other things to do in November and December.
The prototype will be kept by Leo.
