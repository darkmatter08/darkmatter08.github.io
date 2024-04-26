---
layout: page
title: Opportunities in Robotics Foundation Models
description: Robotics Foundation Models RFMs Robotics FMs

---

Foundation models can solve many different tasks with a single model. LLMs like GPT-4 can summarize a doc, translate English to Afrikaans, generate code, and interpret images, solving hundreds of different text tasks with a single model. Previously, each of these tasks would have required a separate model, but the single foundation model outperforms the previous task-specific model.

Robotics Foundation Models (RFMs) bring the foundation model paradigm to the physical world. Currently, most robots are driven by autonomy software designed for each task. A robot driven by an RFM will be able to solve hundreds of different tasks across many different environments. Imagine a single robot that can change your car’s oil, deliver food and supplies to patient rooms in a hospital, and fold laundry in your home. Imagine [zero-shot learning](https://www.ibm.com/topics/zero-shot-learning) in the physical world. This is the promise of RFMs.

Because RFMs are based on transformer models (like GPT-4), they inherit [scaling laws](https://arxiv.org/pdf/2001.08361) in compute and data, and are strong generalizers in new domains. These properties allow for a step-function change over previous autonomy approaches, and will advance us towards general purpose robots, in new form factors, operating in new environments. I explore the implications of this foundational technology for the robotics market and opportunities for startups.

This outline will help guide you through this document.

I. [What are RFMs?](#i-what-are-rfms)

II. [Simulation](#ii-simulation)

&nbsp;&nbsp;&nbsp;&nbsp;a. [Data Generation via simulation](#a-data-generation-via-simulation)

&nbsp;&nbsp;&nbsp;&nbsp;b. [Design and Evaluate novel robots and models in simulation](#b-design-and-evaluate-novel-robots-and-models-in-simulation)

III. [General Purpose Robots](#iii-general-purpose-robots)

&nbsp;&nbsp;&nbsp;&nbsp;a. [RFMs enable general-purpose robots](#a-rfms-enable-general-purpose-robots)

&nbsp;&nbsp;&nbsp;&nbsp;b. [General-purpose robots will create a network of suppliers](#b-general-purpose-robots-will-create-a-network-of-suppliers)

IV. [The Startup Opportunity in Simulation](#iv-the-startup-opportunity-in-simulation)

&nbsp;&nbsp;&nbsp;&nbsp;a. [The Product](#a-the-product)

&nbsp;&nbsp;&nbsp;&nbsp;b. [Stochasticity is expensive](#b-stochasticity-is-expensive)

&nbsp;&nbsp;&nbsp;&nbsp;c. [Simulation is strategic](#c-simulation-is-strategic)

&nbsp;&nbsp;&nbsp;&nbsp;d. [Network Effect - Crowdsourced Reinforcement Learning](#d-network-effect---crowdsourced-reinforcement-learning)

&nbsp;&nbsp;&nbsp;&nbsp;e. [Product Evolution](#e-product-evolution)

V. [Why now?](#v-why-now)

VI. [Resources](#vi-resources)

### I. What are RFMs?

Robotics Foundation Models (RFMs) are Transformer models co-trained on Robotics data. The model takes as input a natural language instruction, like “move the banana onto the plate,” and images from the robot’s cameras, and the model outputs a robotic action, commanding the robot into a particular pose.

The most exciting recent work in RFMs is the RT- series of papers by Google DeepMind. They scaled up RFMs with data from many different robot embodiments, tasks, and data formats, and observed positive transfer. As a made up example, data from a single-arm robot on a pick-and-place task actually helped a humanoid robot fold laundry.

This happened because Transformer models are extremely strong generalizers. And we’re at the very beginning of the data scaling curve for RFMs.

There are two important takeaways from this, with respect to training data:



1. We need more data, and we can generate that data from simulators. The [sim2real gap](https://sim2real.github.io/) will shrink because these models are strong generalizers.
2. RFMs replace the typical perception-planning-controls autonomy stack with a single model trained end-to-end. Therefore, RFMs don’t enforce any intermediate representation; instead, the representation is implicitly chosen by learning. That compute + learning beats human design is the crux of [The Bitter Lesson](http://www.incompleteideas.net/IncIdeas/BitterLesson.html). This also means that there is no need to label the intermediate representations, _which makes data collection much cheaper and therefore more scalable_.

We need data, and simulation can help.


### II. Simulation


#### a. Data Generation via simulation

A 3D simulator will contain an “environment,” e.g. a table with objects on it, a robot, and a programmatically defined goal matching the natural language instruction. The simulated robot is driven to satisfy the goal, generating a sequence of robotics actions. Images of the simulated environment are captured from the simulated robot’s virtual cameras. This triple of natural language instruction, images, and a sequence of actions forms a single training datum.

The simulated robot could be driven by a human, by known good autonomy software for the specific task, or by an existing model, and good samples selected manually via human review, or automatically, by checking if it satisfies the goal.


#### b. Design and Evaluate novel robots and models in simulation

We want to use RFMs to drive all kinds of robots, even if they have a very novel form-factor or are designed to accomplish an unusual task. For example, RFMs should still be able to drive an underwater or space robot, even if they have very different sensors, actuators, and environments.

Instead of building and testing the robot in the physical world, which is costly, time-consuming, not scalable, and may not be possible, we want to build and test robots entirely in simulation, and have high confidence that the result will perform in the real world. This will make robot design much more accessible.


### III. General Purpose Robots


#### a. RFMs enable general-purpose robots

A general purpose robot must handle **novel tasks** in a **dynamic environment**.

While previous autonomy software stacks struggled to generalize to tasks not in the training data, RFMs are co-trained on internet data, giving them world knowledge that may not be present in the robotics training data, helping them perform novel tasks.

In dynamic environments, rule-based hardcoded autonomy software doesn’t work. The unconstrained real-world simply has too much diversity, leading to innumerable edge-cases. RFMs are learning algorithms with the best generalization capabilities, they will make fewer mistakes than other hardcoded or learned systems in dynamic environments.

Overall, RFMs will advance us towards general purpose robots by being excellent generalizers.


#### b. General-purpose robots will create a network of suppliers

General-purpose robots will be deployed everywhere, from hospitals, to factories, offices, airports, and homes. There will be many companies developing and deploying robots, leveraging their industry-specific knowledge, software integrations, and existing relationships. 

Not all of these companies can make the capital and technical investments to develop a whole robot from scratch. Instead, they will rely on a **network of suppliers**. Lowest in the stack will be vendors of generic RFMs. Next in the stack will be suppliers that will sell data and tools to enhance the RFMs, like simulators and proprietary datasets. Next will be suppliers who sell kits with a compute board, sensors, and actuators. Their customers will integrate these kits into their final physical form. Other vendors will sell tele-operation tools, predictive maintenance tools, and other top-level value adds.

Why doesn’t the self-driving industry have such a network? It’s dominated by a few large players like Waymo and Cruise, who are well capitalized and highly vertically integrated. For example, Waymo developed an in-house Lidar instead of using Velodyne, and Cruise developed an in-house ML accelerator chip. The Waymo Driver (Simulator) has 20 billion simulated miles of experience. In contrast, Applied Intuition supplies driving simulators for ADAS development to traditional automakers.


### IV. The Startup Opportunity in Simulation

The opportunity is motivated by three major observations:

1. Simulation allows for training data generation, key to improving model performance.

2. Simulation allows for the design and evaluation of new robots and models.

3. There will be a network of suppliers in the robotics industry.

This suggests the need for a simulation provider who can offer data generation and evaluations.


#### a. The Product

The product is a 3D simulator. Within this simulator, they will be able to design environments (like a table with objects on it) and a robot. They will be able to define “goals” for this environment; e.g. move the banana from the right side to the left side of the table, programmatically. The triple of the environment, robot, and goal may be called a “situation”.

For data generation, the simulated robot could be driven by a human, by known good autonomy software for the specific task, or by an existing model, and good samples selected manually via human review, or automatically, by checking if it satisfies the goal.

For evaluation (testing), the robot will be driven by the model, and will count as ‘satisfactory’ if it meets the goal. Each situation will be randomized, and with more samples (attempts) taken, the user will have a more accurate representation of the model’s true performance. This is similar to sampling-based evals in the code-generation domain.

Both data generation and evaluation will be accessed via API. The situation designer would be accessed via a web interface.


#### b. Stochasticity is expensive

The simulator will have many sources of stochasticity built in. In addition to perturbing small environmental constants (e.g. coefficient of friction, temperature, wind, exact position of objects and robots, amongst others), we will use algorithms like Paired Open-Ended Trailblazers (POET) and Automatic Domain Randomization to ensure diversity in generated data. We may also leverage generative time-series models to add stochasticity to these variables in the time dimension, a relatively under-explored direction.

All of these sources of stochasticity make this a computationally large workload, which requires a large investment in compute and software engineering, and is therefore expensive. A supplier can amortize these costs across many clients. This makes it amenable to being bought instead of built in-house by our clients.


#### c. Simulation is strategic

Simulation is a strategic place to sit in the robotics supply chain because it controls the performance of RFMs, it requires capital investment, it is a scalable software system, and can leverage network effects. Because of these properties, it will capture a significant portion of value in the chain.

Simulation will allow the rapid design and evaluation of new robots and models as well, creating deep customer relationships.

It is a strategic place to conduct research in simulators, sim2real, and RFMs, because any advances can be deployed very quickly to many customers.

And just like in LLMs, robotics companies will need to customize the foundation models for their specific application, by training on domain specific data via fine-tuning and Reinforcement Learning (RLHF). Simulation will enable this.


#### d. Network Effect - Crowdsourced Reinforcement Learning

There is a network effect that we can get by offering both data generation and evaluation.  Specifically, we can create a high-level RL loop against the situations. We could use the goals created by our users as a reward function, and train a policy model against this reward function using PPO or some other RL algorithm. This is a ‘crowdsourced’ version of [Reinforcement Learning from Human Feedback](https://openai.com/research/instruction-following) (RLHF). Users could be incentivized to share their environments because they could receive a better model in return. Because the evals are run on our service, the users' environments are not shared with other users directly, preserving privacy.


#### e. Product Evolution

**Step 1 (short shelf-life):**

Straight re-implementation of [RT-2-X](https://deepmind.google/discover/blog/scaling-up-learning-across-many-different-robot-types/). Brand it “R-1”.

A fully integrated autonomy stack. ROS or other robotics frameworks with “R-1” integrated. This will kickstart the tooling and community around “R-1”.

**Step 2 (core offerings):**

A 3D simulator to design robotic environments, and tools to automatically generate synthetic data for training and simulation.

“Robustified” version of “R-1” with some mix of real and simulated proprietary data and modeling tweaks. Offered standalone or integrated into ROS. Make the “LLama of RFMs” to build goodwill, brand, and community. Brand it “R-2”.

**Step 3 (advanced offerings):**

“Crowdsourced RL” product. Brand it “R-next” or “R-3”.

I expect these three steps to be completed within 18 months of founding.


### V. Why now?

RFMs have two key properties. Firstly, they are strong generalizers; data from one robot in one environment can help the model control a different robot in a new environment. Secondly, they inherit [scaling laws](https://arxiv.org/pdf/2001.08361) from Transformer models.

Therefore, RFMs 1. can control a wide variety of robots, in different environments, on diverse tasks and 2. require large and diverse data to be performant. This is fundamentally different from current robotics approaches, which use domain-specific software stacks trained on limited in-domain data. The first will create a proliferation of novel robot deployments, driving the demand for simulated evaluations, and the second will drive the adoption of simulated data. This will change the structure of the robotics marketplace.

Simulation is a key partner technology of RFMs, and a startup in this highly strategic space can capture a large amount of value in the supply network for robotics.

Why now? Large scale and performant multi-modal models have only become [available in the past 18 months](https://github.com/BradyFU/Awesome-Multimodal-Large-Language-Models/blob/main/images/timeline.jpg); and open-source models generally trail closed-source ones [by ~12-18 months](https://www.reddit.com/media?url=https%3A%2F%2Fpreview.redd.it%2Ftodays-open-source-models-beat-closed-source-models-from-1-v0-87iqgadwb9uc1.png%3Fwidth%3D1262%26format%3Dpng%26auto%3Dwebp%26s%3Dd12db0b9b36eb5e7e2f83e1b81f2e5f31bd195e8). The most promising research is [less than 18 months old](resources). I posit that we’re at the GPT-2 moment for RFMs, at the start of a years-long exponential growth in capabilities, productization, and investment.


### VI. Resources

#### a. Research
**Robotics Transformers**

[Google RT-1](https://blog.research.google/2022/12/rt-1-robotics-transformer-for-real.html)

[Google RT-2](https://deepmind.google/discover/blog/rt-2-new-model-translates-vision-and-language-into-action/)

[Google RT-X](https://deepmind.google/discover/blog/scaling-up-learning-across-many-different-robot-types/)

[PACT](https://arxiv.org/abs/2209.11133)

**Motivating work**

[Masked Visual Pre-Training for Motor Control](https://arxiv.org/abs/2203.06173)

[Real-World Robot Learning with Masked Visual Pre-training](https://arxiv.org/abs/2210.03109)

[LATTE](https://arxiv.org/abs/2210.03109)

[SayCan](https://say-can.github.io/)

[Survey Paper](https://arxiv.org/pdf/2312.07843)


#### b. Companies in Robot Foundation Models

**Large Players**

[nVidia Gr00t](https://developer.nvidia.com/project-gr00t)
* Leveraging nVidia Isaac for simulation.

[Google X/DeepMind](https://deepmind.google/discover/blog/rt-2-new-model-translates-vision-and-language-into-action/)
* Origin of early research. Pursuing deep partnerships with robotics companies for deployment. Ample access to compute.

[Tesla Optimus](https://twitter.com/tesla_optimus)
* Not using RFMs yet; adapting tooling from FSD/Autopilot effort, including simulators.
* Vertically integrated; [attempting to deploy to factories.](https://www.teslarati.com/tesla-bot-optimus-field-test-factories/)

**Robotics Startups**

[1X](https://www.1x.tech/)
* Eric Jang, a researcher from Google Robotics, moved here.
* Currently deployed robot EVE does not use RFMs.

[Figure](https://figure.ai/)
* Not using RFMs yet. [Deploying to BMW factories](https://www.prnewswire.com/news-releases/figure-announces-commercial-agreement-with-bmw-manufacturing-to-bring-general-purpose-robots-into-automotive-production-302036263.html)

[SkildAI](https://www.linkedin.com/in/skild-ai/)
* Pittsburgh based; very little information available.

[Covariant](https://covariant.ai/)
* Released [RFM-1](https://covariant.ai/insights/introducing-rfm-1-giving-robots-human-like-reasoning-capabilities/). Likely using robotics data from deployments.

**RFM Startups**

[Physical Intelligence](https://physicalintelligence.company/)
* Star team, including co-authors of the RT- papers. Small team developing an RFM.

All these companies are actively recruiting.
