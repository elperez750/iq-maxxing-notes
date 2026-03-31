
2026-03-23 19:32

Status: #Adult  

Tags: [[Entrepreneurial]], [[Economic Moat]], [[AI]]

# [[Jensen Huang]] and Nvidia's Dominance

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

###### What I got, is that NVIDIA is essentially co designing with the whole company. One team is working on the software side (CUDA) another team is working on the hardware. Another on research and development of GPUs and how to make components smaller and more efficient. It truly is a well oiled machine and a big system


###### Nvidia has experts on all. Such as GPU and CPU. All people attack of problem because the company is doing extreme co design. Co design is multiple people of all disciplines to solve a problem. Nvidia is adapting to the environment


###### NVIDIA is a company that sees the value in investing in research and development. I think the practicality of this is to improve their hardware sure, but that means that they are in a better position to handle shifts in the market. From AI generation to AI agents.


## CUDA

- A computing platform is all about developers, they come because an install base is large. Developers want to reach enormous amount of people

###### Makes sense. Put them in GeForce GPUs that gamers are buying and now they have CUDA.

- x86 is the defining architectures. Incredible designed. Install base defines an architecture


- CUDA was competing with OpenCL

- By that time GeForce GPUs were successful

###### GeForce was the foundation of gaming.

- Jensen wanted to put CUDA on GeForce, so that people that bought the GPU would have access to it. So NVIDIA could slowly grow their base


- CUDA increase cost of the gross profit dollars, which consumed the companies gross profit dollars. Company was worth 8 billion dollars

- CUDA became the platform and foundation for the AI revolution


- Jensen Huang lays the foundation of new plans before he makes a move. This is so that the company has an idea of what direction the company might be going in, and so that noone is left in the dark.


- CUDA is really flexible

- Parallel computing platform + programming model + toolchain for NVIDIA GPUs.
- Lets you write general-purpose code (C/C++/Python, etc.) that runs on GPUs, not just graphics.
- NVIDIA built layers on top: math libraries, deep learning libraries, debuggers, profilers, SDKs.

## Why NVIDIA  became a Moat

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

###### In the pre training scaling law, people thought that high quality data would be a blocker. A lot of data will have to be synthetic, meaning, it will come from the AI models themselves

###### I think that this is already happening at a large scale. I mean, there's only so much data in the world that is generated by humans. The thing that worries me is how unique now will the training data be related by AI? As much as humans say of lot of the same things, there is a uniqueness that the AI might not be able to capture

###### I see this a lot with my responses. It seems like when I ask for book recommendations, I get a lot of books that are good, but are also popular at the same time. A professor in a certain field might be able t give you books that might not be as popular but are gold with the things you are learning.


###### So this means that the training will be limited by the compute and not the data. This is related to [[Geopolitics]] because I think that eventually, the global hegemons might try to conquer Greenland for their AI datacenter needs. After all, Greenland provides natural cooling since it is so cold.


- agentic scaling law is multiplying AI

- AI model architectures being invented once every 6 months, so you need to anticipate what will happen.

- NVIDIA Vera Rubin pod includes 40 racks, 1.2 quadrillion transistors, about 20,000 NVIDIA dies, 1,152 GPUs, 60 teraflops and 10 PB/s scale-up bandwidth

- NVIDA wants to improve tokens per second. They want to push token costs now


###### So to lower token costs what does this entail? Make the models faster? Well thinking through this logically, if the models are faster, that means that less compute and power is wasted, meaning that tokens can be cheaper due to the savings in power and compute? This makes sense from an economic standpoint.


- HBM4 is high bandwidth memory integrated with Rubin GPUs to provide massive local memory bandwidth

- LPDDR5X is a low power system DRAM used on grace/vera CPU modules as fast, energy-efficient main memory. 

###### I think for the next notes I won't include technical jargon. It might just be simple to focus on what these new innovations, memory increases, and such are doing for NVIDIA as a business, because that is the big picture.


## Energy problem in AI

- power grid is designed for worst case condition

- using EIA's definition of load factor and EIA's latest U.S. data (2025), the us Grid's average load is 59.8%

- Jensen wants to use excess power for the data centers

- "We need things to be as complex as possible but as simple as possible"


###### This quote from Jensen stuck with me, because as much as people say that simplicity is not complex enough, and that complexity is too impractical, one must reach the in between point here. It's just something that makes sense but is mind blowing


## The tech industry in China

50 percent of the worlds researchers are Chinese

###### Well they do have the largest population in the world. The thing I am confused about is how is China at the forefront of AI research if they technically are not working with the same data? Meaning that they are probably working with heavily censored data.
 

- Mayor economy is a core component of China's hybrid economic model where mayors and local government officials take a direct, [[Entrepreneurial]] role in driving economic growth within their jurisdictions.

###### This makes sense. When people on the small scale have direct control over economic growth, then that effect will cascade


- This model is described in The New China Playbook, a book written by Keyu Jin. She writes the following : "Adams Smith's concept of invisible hands working behind the scenes is, in the case of China, replaced by the thousand-arm Buddha's extended and very visible hands"

###### Need to watch that podcast episode next with Keyu Jin and Lex.


- The culture in China has family first, friends second and company third.

- The open source community is better in China. Fastest innovating country in the world. Excellent education

###### They also do not have copyright laws I thing.

###### As much as people say that culture does not  play a role in an economy, China is a great example of how education can shape a nation.


## TSMC

- Deepest misunderstanding is tech is all they have. Their ability to orchestrate demands of 100s of companies with high throughput and excellent customer service is miraculous

- Culture is tech focused but customer service oriented. Most companies are not both. 


## NVIDIA's biggest moat

- The single most important property is the install base off the computing platform, aka CUDA

- the ecosystem is the second. They're in every big companies computer. Even in satellites. Covers every industry


## Will NVIDIA reach market cap of 10 Trillion

- Biggest computing company in history

Two foundational technical reasons:

- First: Computing went from file retrieving to generative based computing system. Means we need more storage and computation 

- Second: Computers were warehouses, now they are factories. Now used to generate revenues 


###### Well computers have been the backbone of our world now for 20 years basically, maybe even more time. They have become more and more important as they became more engrained in government and banks. The blue collared guys can talk all the shit they want but the reason for more growth in their sector is due to data centers being built and more offices for expanding tech companies.


- NVIDIAS success is vital to the United States

###### Well before the FED had to worry about bailing out banks that were essential to the United States, meaning [[Too Big To Fail]], so what does this mean now because technology companies are the most influential and the ones with the most money, so I'm guessing the FED will bail them out too in a time of crisis?

###### Kind of crazy that NVIDIA basically has more influence and wealth than the GDP of a lot of nations.

- They are creating thousands of jobs


## AGI

- This is essentially an AI system that can do your job

- This means that it has access to your computer and complete tasks there. Pretty much a worker.

###### What does this mean for security? I mean AI agents being able to crawl around your PC? It's crazy that people are allowing this on their computers. OpenClaw is an example of this.


- AGI might be used to make money; What i mean is that they will look for jobs, or becoming influencers


## The future of programming

- Jensen basically says that software engineers will not be replaced since their main job is to solve problems, not write tons of code.

- "Go use AI. Go see what it can do for your job"

##### Jensen is obviously a big advocator of AI, and it makes sense that he would want his employees to be proficient, but what about the critical thinking skills? Those still need to be sharpen. There needs to be a balance with using AI in a way that automates the repetitive parts but that allows for critical thinking, not conformity.

- "If the job is the task, the job will disappear, if the job includes task, AI will simply make your life easier."

###### As I reflect on the podcast and on AI in general, I honestly believe that we would have been better without AI in our society. Sure it helps make us more productive, but part of learning was the friction involved in researching and going through resources to understand. As controversial as it sounds, I would rather live in that timeline than this one, because I don't believe the net good of AI will be better than the damage it has done, or will continue to do

###### First, there is the problem with cooling these large data centers that have thousands of GPUs running, which is obviously an environmental issue as much water must be used in order to cool down these places. Also the fact that more and more children in grade school are resorting using AI to copy and paste answers for homework assignments, and some teachers encouraging it. I understand that part of the reason that they are encouraging it is that they want students to be ready for the real world where AI will be used profusely in the work place. I've experienced this with a lot of my Computer Science classes where coding with AI is the norm now, but I think it is weird for teachers to focus on this, instead of critical thinking skills, which are the foundation for everything.


## Will AI feel human emotions

###### They will understand the feelings, but not feel them

- What is the subjective experience?

- What is intelligence?

- Intelligence is a commodity. Its a functional thing






























