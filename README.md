# MAPR Overview

This repository contains a breakdown of all results and important literature that was gathered during my master of applied research in engineering sciences. Parts of this repository will be not be finished and functional.

Modern deep neural networks (DNNs) have basically become the go-to solution for any application
depending on big data analysis, because of their highly effective manner of solving complex
problems. That said these models also come with major deficiencies regarding their vulnerability to
adversarial examples. Even though extensive research has been ongoing, until now, the attack
algorithms are winning this arms race. The solution to this problem might be hidden within methods
and techniques that were developed to solve another apparent shortcoming of DNNs - their inability
of explaining or justifying the rationale behind their decision-making process. Explainable artificial
intelligence (XAI) as a research field aims to produce a suite of techniques to enhance the
interpretability of traditional AI – practices. This research work tries to further uncover the connection
between XAI and adversarial attacks by analyzing and implementing promising XAI techniques that can be used to
enable DNNs to withstand modern adversarial attack algorithms.

Furthermore, most of the recent advancements in the field of XAI regarding the creation of visual explanations have prioritized interpretability in image classification tasks, with little development in other important tasks like image segmentation. So this work will also try and provide further insight into the topic of XAI and its capabilities to interpret segmentation models.

The research approach and implementation can be broken down into 4 major parts:

 - **[Neural Networks](https://github.com/VascoDaGama94/MAPR/tree/main/neuralnetworks):** This section will include data sets and network architectures used to achieve the task of an autonomous driving vehicle. The focus will be on efficiently operating segmentation networks.
 - **[XAI](https://github.com/VascoDaGama94/MAPR/tree/main/xai):** This section will present some foundational and general knowledge about the research field of interpretable/explainable artificial intelligence
 - **[Adversarial Attacks](https://github.com/VascoDaGama94/MAPR/tree/main/adversarialattacks):** Here some attack methodologies will be presented. Also focusing on image segmentation and efficiency
 - **[ROS Racecar](https://github.com/VascoDaGama94/MAPR/tree/main/ros_racecar):** This section includes necessary knowledge to integrate the network into the Hardware used for the real-world application.
