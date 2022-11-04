---
layout: post
title: "State of Industrial Robotics 2022"
author: "Marko Simic"
categories: journal
tags: [documentation,sample]
image: state-of-industrial-robotics-2022.png
---

Robotics and industrial automation are fascinating topics. We’ve all seen videos of Boston Dynamics’ [impressive robots](https://youtu.be/tF4DML7FIWk) and heard stories about [ultra-efficient factories](https://youtu.be/j62U089HDx0) of the future. Images like that captivate our minds and make it easy to think that robots are already widespread and displacing large segments of the workforce. The reality though might be a bit different.

That’s why in this post, we will make a fun comparison between what robotics **industry pundits** are saying, what **business scholars** are finding, and what **robotics researchers** are thinking about. Then, in the end, we will tie the narrative, draw some conclusions, and offer a biased solution.

## World of Robots

According to the International Federation of Robotics (IFR) [World Robotics 2021 report](https://ifr.org/ifr-press-releases/news/robot-sales-rise-again),
>around 3 million industrial robots were operating in factories worldwide by 2021, with 384,000 units shipped globally in 2020.

Asia remains the world’s largest market, with **China being the biggest adopter of industrial robotics**. On the other side of the world, North America experienced a slow down in sales during 2019 and 2020, most likely because of the pandemic uncertainties, but market expectations are positive overall. It is also worth mentioning that most robots are employed in the automotive and electronics industry.

Besides statistics about industrial robotics, IFR, among other things, creates a list of significant trends in robotics for the upcoming year. They are always interesting to read and provide insight into the industry’s direction. For example, major trends in robotics for years [2022](https://ifr.org/ifr-press-releases/news/top-5-robot-trends-2022), [2021](https://ifr.org/ifr-press-releases/news/top-5-robot-trends-2021), and [2020](https://ifr.org/ifr-press-releases/news/top-trends-robotics-2020) were:

![Robot Trends]({{ site.github.url }}/assets/img/robot-trends-table.png)

Based on the numbers and trends reported, we can see that the **robotics industry is moving in a positive direction**, and we can expect widespread adoption of robots in the manufacturing, logistics, and service industry.

## This is Fine

![This is Fine]({{ site.github.url }}/assets/img/robot-this-is-fine.jpg)

Meanwhile, Suzanne Berger and Benjamin Armstrong from MIT were interested in the actual state of automation in United States manufacturing plants. Although, as we have seen above, uptake in robotics is increasing and automation is taking hold, they found that
>fewer than 10 percent of US manufacturers, particularly small and medium enterprises (SME), have any industrial robots.

And in the United States, SME manufacturers constitute 98.4 percent of all manufacturing establishments in the US, and they employ 43 percent of all manufacturing workers. So, naturally, they posed a question, **why are the robots missing?**

Through their industry survey, they uncovered **four major issues** the US manufacturing industry faces when it comes to the adoption of robots:

1. Most SMEs are suppliers with high-mix/low-volume manufacturing, while most robots are still relatively inflexible and difficult to program. Hence, buying a robot for a single operation is not economically rational.
2. The costs of integrating the robot into the factory make solutions expensive. The purchase price of the robot is usually only 25% of the total cost of integrating it into the production line.
3. A high-mix/low-volume supplier is dependent on customers whose orders vary unpredictably, and contracts can end suddenly, so heavy investment in equipment for making any particular product is unwise.
4. Manufacturers are reluctant to invest in new equipment because they cannot find workers with the right skills to work on it.

At first glance, we could conclude that there is some discrepancy between the IFR-reported statistics and findings of Berger and Armstrong, but in fact, they complement each other. This is because **most robot sales and installations are in the automotive and electronics industry, dominated by large companies** that can invest capital in automation and have standardized production processes.

To improve robot adoption in SMEs, we need robotic solutions that are **more versatile, easier to use, and cheaper to own**. All of which are, in fact, trends that the robotics industry is moving to. And what is enabling these trends are **advancements in artificial intelligence (AI), better sensors, and more powerful compute**. So, let us now look at how artificial intelligence researchers are thinking about the current state of robotics.

## Enter Science

![Enter Science]({{ site.github.url }}/assets/img/robot-enter-science.png)

Paper From Machine Learning to Robotics by Roy et al. identifies and explores the shortcomings of current AI in robotics and presents several hypotheses on how to overcome them.

Even though robots are getting better each year, they are still far from being robust, efficient, and truly intelligent.

>The intelligence of a system is a measure of its skill-acquisition efficiency over a scope of tasks, with respect to priors, experience, and generalization difficulty. Chollet 2019.

Unfortunately, most, if not all, industrial robots can perform only a specific task (or few) and only in a relatively controlled environment like a robot cell or warehouse. That is, they are not very intelligent at present.

Machine learning is one of the key technologies that enabled the current novel robotic applications like pick-and-place of random items from unstructured environments or free navigation in the warehouse populated by humans. But even these systems, when encountered with situations outside of their operational design domain, **run into problems of brittleness and lack of versatility**. The reason for these problems is that typical machine learning approaches:

1. Do not consider operation under conditions significantly different from those encountered during training.
2. Do not consider the often substantial, long-lasting, and potentially safety-critical interactions during learning and deployment.
3. Do not require ready adaptation to novel tasks.
4. Do not require an effective and efficient update to their world models through targeted and deliberate actions.

The authors identified four crucial components for creating better (i.e., robust, versatile, general) robots: **inductive biases, cognitive architecture, representations, and morphology**. Based on that, they argue that to have more effective and efficient learning that will result in the aforementioned better robots, the following has to be taken into account:

1. We need new and explicit inductive biases based on action and perception.
2. An embodied intelligence that learns must do so at multiple levels of abstraction and have the ability to effectively amortize reasoning while maintaining the introspection and capability to perform more elaborate inference on demand.
3. Some form of symbolic logic grounded in physical perception and action is essential for scalable representations that enable robots to learn and generalize effectively in the real world.
4. Physical design of robots (i.e., morphology, actuators, and sensors) significantly complements effective learning and should not be treated in isolation.

They also point out that we need better methods for assessing robot learning and performance. More specifically, standard methods for verification, validation, and benchmark-based performance evaluation are not suitable for embodied agents operating in a dynamic environment.

## What Did We Learn?

Industrial automation and robotics are picking up steam, and many companies are looking to improve their operation and lower costs at the same time. Moreover, the COVID-19 pandemic surfaced all the inefficiencies in current manufacturing and exposed the brittleness of our logistics systems. As a result, **investments in robotic space are increasing**, and we are likely to see rapid advancements in robotic capabilities.

But these production gains and advanced automation solutions are still reserved mostly for large companies that deal with high-volume standardized production and who can afford the current steep price of automation. Meanwhile, small and medium companies are unable to reap the benefits of robotic systems due to their cost, complexity, and rigidity.

Researchers are aware of the current shortcomings and are thinking (and working) hard to find solutions to the most pressing problems robotics is facing right now. However, the goal of academia is not to make robotics products directly but to create new knowledge and technology. That is why robotics research is not directly applicable to the industry environment, and there is an **excellent opportunity for innovative and agile companies** to transform cutting-edge research into great products that answer industry needs.

### References

Berger, S., Armstrong, B., Kaiser, D., & Shah, J. (2022). The Puzzle of the Missing Robots. MIT Case Studies in Social and Ethical Responsibilities of Computing, (Winter 2022). https://doi.org/10.21428/2c646de5.9461c9fb

Roy, N., Posner, I., Barfoot, T., Beaudoin, P., Bengio, Y., Bohg, J., … & Van de Panne, M. (2021). From Machine Learning to Robotics: Challenges and Opportunities for Embodied Intelligence. arXiv preprint arXiv:2110.15245.

Chollet, F. (2019). On the measure of intelligence. arXiv preprint arXiv:1911.01547.
