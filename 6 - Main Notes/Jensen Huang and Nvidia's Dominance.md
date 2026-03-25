
2026-03-23 19:32

Status:

Tags: [[Entrepreneurial]], [[Economic Moat]], [[AI]]

# Jensen Huang and Nvidia's Dominance

##### Author: Lex Friedman


## References
https://www.youtube.com/watch?v=vif8NQcjVf0

https://blog.2600hz.com/amdahls-law-and-parallel-computing

### Notes


## Amdahl's Law

*  If only a fraction of a workload can be accelerated, the overall speedup is bounded by the rest of the workload
#### Intuitive example

Say a task takes 100 seconds:

- 40 seconds are parallelizable (p=0.4p=0.4)
    
- 60 seconds are inherently serial (1−p=0.61−p=0.6)
    

If you make the parallelizable part 10× faster (s=10)(s=10):

- New time = 60+40/10=60+4=6460+40/10=60+4=64 seconds
    
- Overall speedup = 100/64≈1.56100/64≈1.56×
    

So huge work on the parallel part only yields a modest overall gain because the serial 60 seconds dominates. This is the “[[Diminishing Returns]]” behavior: once the serial bottleneck dominates, adding more parallel hardware helps less and less.

![[Pasted image 20260323223650.jpg]]

What is extreme co design

##### What I got, is that NVIDIA is essentially co designing with the whole company. One team is working on the software side (CUDA) another team is working on the hardware. Another on research and development of GPUs and how to make components smaller and more efficient. It truly is a well oiled machine and a big system





Nvidia has experts on all. Such as GPU CPU

All people attack of problem because the company is doing extreme codesign


Nvidia is adapting to the environment


This is why they are now an AI factory

Nvidia started as accelerator company. The domain is too narrow

Market size dictates research and development size


##### NVIDIA is a company that sees the value in investing in research and development. I think the practicality of this is to improve their hardware sure, but that means that they are in a better position to handle shifts in the market. From AI generation to AI agents.


## CUDA

A computing platform is all about developers, they come because an install base is large. Developers want to reach enormous amount of people

x86 is the defining architectures. Incredible designed. Install base defines an architecture


CUDA was competing with OpenCL

By that time GeForce GPUs were successful


Jensen wanted to put CUDA on GeForce, so that people that bought the GPU would have access to it. So NVIDIA could slowly grow their base


CUDA increase cost of the gross profit dollars, which consumed the companies gross profit dollars. Company was worth 8 billion dollars

CUDA became the platform and foundation for the AI revolution


Jensen Huang lays the foundation of new plans before he makes a move. This is so that the company has an idea of what direction the company might be going in, and so that noone is left in the dark.


Cuda is really flexible


# CUDA and NVIDIA's Moat

## What CUDA Is
- Parallel computing platform + programming model + toolchain for NVIDIA GPUs.
- Lets you write general-purpose code (C/C++/Python, etc.) that runs on GPUs, not just graphics.
- NVIDIA built layers on top: math libraries, deep learning libraries, debuggers, profilers, SDKs.

## Why It Became a Moat
- Standard platform: HPC and AI communities standardized on “NVIDIA GPU + CUDA”.
- Huge ecosystem:
  - Tons of code, research, and products written assuming CUDA.
  - Universities teach CUDA; many engineers learn it as the default GPU model.
- Forward compatibility:
  - Older CUDA code keeps working and getting faster on new NVIDIA GPUs.



## Very Rough Timeline
- Early 2000s:
  - GPGPU done via graphics APIs (OpenGL/DirectX “hacks”).
- 2004–2006:
  - CUDA project inside NVIDIA to expose GPUs as general-purpose parallel processors.
- 2007:
  - CUDA 1.0 public launch; first CUDA-capable GPUs (e.g., GeForce 8 series).
- 2008–2012:
  - HPC and scientific computing adopt CUDA.
  - NVIDIA releases core libraries like cuBLAS, cuFFT, etc.
- 2012–2015:
  - Deep learning boom; AlexNet and others use NVIDIA GPUs.
  - cuDNN (deep learning primitives) released; frameworks start plugging into it.
- 2016–2020:
  - Major frameworks (TensorFlow, PyTorch, etc.) ship strong CUDA support.
  - NVIDIA adds TensorRT, NCCL, DeepStream, and other AI/ML SDKs.
- 2020–2026:
  - LLMs and generative AI mostly trained and served on NVIDIA GPUs using CUDA stack.
  - Tooling evolves (e.g., PyTorch + TensorRT, newer CUDA versions for new GPU features).

## Built on CUDA (Layers)

- Core:
  - CUDA language extensions, runtime/driver APIs, kernel launch model, memory model.

- Libraries:
  - cuBLAS, cuFFT, cuSPARSE, cuRAND, cuSOLVER, NCCL, etc.

- AI/ML Libraries & SDKs:
  - cuDNN (deep learning primitives)
  - TensorRT (inference optimization)
  - DeepStream (video analytics)

- Frameworks (using CUDA under the hood):
  - TensorFlow, PyTorch, JAX, Keras, Caffe, MXNet, etc.

- Applications:
  - Scientific simulation, rendering, video processing, vision, speech, recommendation, LLMs, etc.




## Blockers to AI scaling laws


* Pre-training scaling. Get models trained Scale and scaling efficiency
* Post-training scaling: Fine-tune pretrained models. Quantize to NVFP4
* Test-time scaling. "long thinking": Optimize MoE models NVL72, Dynamo
* Agentic Scaling: "Ai talking to Ai": Low latency and large context required at scale

In the pre training scaling law, people thought that high quality data would be a blocker

A lot of data will have to be synthetic

Most data that is being used for training is synthetic

Training will be limited by compute, not  data

Inference is thinking and thinking is hard.


Pretraining is memorization and generalization. You are looking for patterns.

Agents create sub agents


agentic scaling law is multiplying AI

AI model architectures being invented once every 6 months, so you need to anticipate what will happen.


NVIDIA Vera Rubin pod includes 40 racks, 1.2 quadrillion transistors, about 20,000 NVIDIA dies, 1,152 GPUs, 60 teraflops and 10 PB/s scale-up bandwidth


NVIDA wants to improve tokens per second. They want to push token costs now


HBM4 is high bandwidth memory integrated with Rubin GPUs to provide massive local memory bandwidth

LPDDR5X is a low power system DRAM used on grace/vera CPU modules as fast, energy-efficient main memory. 



## Energy problem in AI

power grid is designed for worst case condition


using EIA's definition of load factor and EIA's latest U.S. data (2025), the us Grid's average load is 59.8%

Jensen wants to use excess power for the data centers


"We need things to be as complex as possible but as simple as possible"


##### This quote from Jensen stuck with me, because as much as people say that simplicity is not complex enough, and that complexity is too impractical, one must reach the in between point here. It's just something that makes sense but is mind blowing


## The tech industry in China

50 percent of the worlds researchers are chinese

 

Mayor economy is a core component of China's hybrid economic model where mayors and local government officials take a direct, [[Entrepreneurial]] role in driving economic growth within their jurisdictions.

##### This makes sense. When people on the small scale have direct control over economic growth, then that effect will cascade


This model is described in The New China Playbook, a book written by Keyu Jin. She writes the following : "Adams Smith's concept of invisible hands working behind the scenes is, in the case of China, replaced by the thousand-arm Buddha's extended and very visible hands"


Insane competition internally


have a social culture with family first, friends second and company third.

The open source community is better in China. Fastest innovating country in the world. Excellent education

##### As much as people say that culture does not  play a role in an economy, China is a great example of how education can shape a nation.



## TSMC

deepest misunderstanding is tech is all they have. Their ability to orchestrate demands of 100s of companies with high throughput and excellent customer service is miraculous

Culture is tech focused but customer service oriented. Most companies are not both. 


## NVIDIA's biggest moat

The single most important property is the install base off the computing platform, aka CUDA

the ecosystem is the second. They're in every big companies computer. Even in satellites. Covers every industry


## Will NVIDIA reach market cap of 10 Trillion

Biggest computing company in history


Two foundational technical reasons:

First: Computing went from file retrieving to generative based computing system. Means we need more storage and computation 


Second: Computers were warehouses, now they are factories. Now used to generate revenues 



 































