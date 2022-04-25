# Efficient Image Segmentation
Since this work aims to produce a real-world application using the [Jetson AGX Xavier Developer Kit](https://developer.nvidia.com/embedded/jetson-agx-xavier-developer-kit), the computing ressources will be limited.
Therefore the selection of an efficient segmentation network is of utmost importance for the success of the project.
For this sake a suite of models were looked at and analyzed as well as commisioned. Especially the possible infernce speed and therefore the fps number with regard to the number of necessary parameters utilized for the compution were under focus. The lesser the number of paramteres needed by the network the better the chances the network will work properly on the embedded GPU. 
In the presented directories the different network architectures and a preview of thier results will be presented.

## Resources

 - https://github.com/xiaoyufenfei/Efficient-Segmentation-Networks
 - https://github.com/meetps/pytorch-semseg

