Zillians GPU Virtualization Middleware (vGPU)
=========================================================

Project Overview
----------------

GPU has been adopted by several cloud operator like Amazon and PEER1. For Amazon, they announced GPU instances to serve the need of running GPU-based application in their EC2 cloud. However it's pretty expensive and it’s fixed to a single configuration, which contains exactly two NVIDIA Tesla M2050. This is due to a fact that GPU does not have proper support of virtualization technology, such as SR-IOV, and also the number of available GPU in a single chassis is quite limited. 

Zillians vGPU solution solves all that limitations and brings them on-demand GPU computing. If you've heard research works like rCUDA or GViM, we did pretty much the same thing as theirs, which is called API remoting (forwarding API calls through network to remote). However, vGPU have re-implemented it from scratch and have done much more than that. 

In order to reduce the communication overhead between the GPU server and client, we dropped TCP and took full advantage of Infiniband RDMA (Read/Write & Atomic) offloading (and probably GPUDirect technology) to avoid unnecessary memory copy and time-consuming TCP packet processing. Also, unlike others, we require ZERO change to the GPU application source so that you can run your GPU application of use your close source GPU library with no hassle. We support both CUDA Runtime and Driver API and emulate the exactly the same behavior of native CUDA application such as kernel concurrency and stream overlap. Finally, our VGPU solution provides a simple and intuitive interface for you to manage GPU resources in an extremely flexible manner and also supports easy cloud integration with RESTful APIs. 

So for cloud infrastructure provider, you can have various GPU configurations and flexible GPU resource pricing plans to minimize your asset investment and maximize the utilization in the same time. For those who wants to deploy private GPU cloud for research purpose, you can deploy VGPU solution to mange your GPU computing resources among researchers by providing an unique key for each of them and change the assigned GPU resources through VGPU web interface.

Dependencies
------------
* Boost C++ Library v1.47 or later
* NVIDIA CUDA SDK 4.0 or later
* Apache Log4cxx
* OFED 1.5.2 or later

Build
-----


Installation
------------


Usage
-----


Testing
-------


Contributing
------------