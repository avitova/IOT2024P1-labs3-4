# System Architecture of IoT - Labs
## Goals and Overview

The emerging and existing IoT frameworks share some central IoT architectural
features. A central pattern seems to be about discovering, connecting,
monitoring, controlling, and/or interacting with a system of _smart things_ or
_Things_ (with capital T), where a Thing is an abstract notion of a digitally
augmented physical object. Digital augmentation is one or more combinations of
sensors, actuators, computation elements, or communication interfaces attached to
the physical object. So, a Thing can be a circuit package with one sensor, or
multiple sensors and actuators, or even a group of devices mimicking a physical
object.

[Three
patterns](https://www.w3.org/Submission/wot-model/#web-things-integration-patterns)
emerge when it comes to binding the Things together. Direct Connectivity refers to
a pattern where each Thing is directly connected to another Thing. Each Thing
has its own application program interface (API) and they communicate with each
other using a standardized API. However, this is indeed the most difficult
approach due to diverse communication standards, lack of processing and
operational power on the devices to support a full-fledged networking stack and
lack of standardization of the API.
[W3C](https://www.w3.org/Submission/wot-model) is coming up with one such
standard and is yet to be ratified. 

Gateway-based connectivity is the second pattern, where a Thing cannot offer an
API directly and sits behind an intermediary. The gateway mimics the Thing and
provides an API on behalf of the Thing. The last common pattern is 
cloud-based connectivity. This is similar to a gateway approach, the cloud
service provides the API for the Things. The difference lies in the fact that
the gateway can be physically closer to the Things. The interaction between
the gateway/cloud and the Things themselves could be orchestrated through tightly
coupled, proprietary communication protocols, that are lighter on power and
computational load when compared to a full internet stack.

In the lab, we will focus on the cloud and gateway pattern. We will use the MQTT
protocol to directly interact with the devices first and then subsequently
conduct the interactions through a gateway. In the process, the goal is to
recognize some good practices when it comes to deploying a Thing network and
this is demonstrated using Amazon's IoT and Greengrass product. We will cover
common security practices that involve authorization and authentication issues.
We will also touch upon elastic edge computing if time permits.

Concretely, the lab exercises are designed to achieve the following learning
goals:

1. Lab 1: Get a working understanding of the MQTT protocol. Setup a rudimentary
   publisher and subscriber using an openly available broker.
2. Lab 2: Establish a secure MQTT connection and understand various parts of
   the setup
3. Lab 3: Establish a MQTT connection that is safe from (unintended) snooping
   and is private using a gateway.
4. Lab 4: Setup an edge - a local computing platform on the gateway for your
   devices to offload its computation. Connect a device to the edge and perform
   some computations. 

## Grading and Expectations

### Lab reports
The lab work is graded based on a submitted report (one report per lab/group) as well
as the code you have in your repository. The report is written in Markdown format in the files `Report_labN.md` files. 

Note that the last committed version on the `main`-branch at the deadline is used for grading.

Your code should be placed in a subfolder named `code/Lab*` (where `*` is the lab number) 
in the main branch.

Each lab exercise has a set of questions that is to be answered, to demonstrate a working knowledge of the concepts involved. You are
encouraged to provide any pictures, graphs, screenshots, diagrams, etc. that
help explain your solution. If you use content (pictures, graphs, etc.)
from other sources, remember to properly cite and provide references to the used
external sources. Refer to the code you have in your repository using links. 

### Learning reflections
You should also provide a reflection on what you learned during these labs in 
the file `lab_reflection.md`. This file should provide answers to the following questions:

1. Have you learned anything new?
2. Did anything surprise you?
3. Did you find anything challenging?
4. Did you find anything satisfying?


The report and reflections should contain the full name of each group member.

For the deadline, see Moodle. Note that each group will also need
to submit a link to your repo in Moodle before the deadline.

## Setup your computer 
To perform lab exercises, you need to set up your computer. No extra computers will be provided and it is your responsibility to set up your computer. It is assumed that you know some basic commands of Linux. 