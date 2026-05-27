1. Clarify the novelty more sharply: The paper currently lists many contributions: embedded architecture, cache, virtual receivers, energy model, Wi-Fi runtime experiments, and NR experiments. These are all useful, but the manuscript sometimes reads as if it is trying to do too much at once. I think the novelty should be organized around three main contributions:

a. Simulation framework contribution: embedding Sionna RT inside ns-3 rather than communicating with an external Python process.
b. Computational-efficiency contribution: displacement-based cache and adaptive virtual receivers to reduce ray-tracing calls.
c. Evaluation contribution: demonstration on runtime scaling and NR energy/performance trade-offs.

The introduction already states the research question reasonably well: how to reduce ray-tracing overhead for packet-level simulation, and how deterministic multipath changes NR performance and energy conclusions compared with conventional ns-3 propagation models. This should become the guiding thread of the entire paper.

2. THe abstract you wrote was too long, grammatically uneven, and contains too many implementation details. It also begins with generic 6G motivation. A journal abstract should move quickly from problem to method to results to implication. I have rewritten the abstract. You can take a look at it.

 

3. The current title is understandable but generic. It does not highlight the strongest novelty: the embedded ns-3/Sionna RT integration and the ray-traced packet-level simulation. Something along the line: "Embedded Ray-Traced Propagation for Packet-Level 5G/6G Simulation in ns-3." You can think and come up with something better as well.

 

4. The section on Background/Related work needs major rewriting. It currently reads like a textbook explanation of MIMO, ray tracing, ns-3, 5G-LENA, and Sionna RT. For a journal submission, the background should be more selective and critical. I would separate background from related work:

a. Background: short explanations of ns-3/5G-LENA, Sionna RT, and ray-traced propagation.
b. Related work: comparison against ns3sionna, Simu5G-based approaches, stochastic channel models, and other ray-tracing/network-simulation couplings.


The Simu5G discussion should be softened. Statements such as “the framework is very rigid” or “lack of native support” need references and should be phrased more neutrally. 

The background also contains many language errors, for example “approache,” “hightlighting,” “improtant,” “movment,” “statical,” “Eventhough,” “lage-scale evalution,” “probalistic,” “diffrations,” “enviorment,” and “modiblity.” These issues occur frequently enough that the whole section needs careful proofreading.

5. Even in the Methodology section, the writing needs to be more precise. Some sentences are difficult to follow because they are too long or because the grammar obscures the meaning. For example, the description of cache refresh and virtual receivers should be written in a more algorithmic style. I recommend adding one or two algorithms, like Propagation query with coherence cache or  Adaptive virtual receiver generation

 

6. The experimental section needs some revision in the following aspects.

a. The paper should be careful when saying that sionnart is faster than pure ns-3 in stationary cases. You already note that this is due to caching, not because ray tracing is intrinsically faster than Friis. This caveat is important and should be emphasized to avoid reviewer criticism.
b. The NR evaluation uses one gNB and 20 UEs, with gNB arrays of 2×2, 4×4, and 8×8, and three environments: free-space, urban macro, and urban micro. This is a reasonable setup, but the paper should justify the parameters more clearly, especially the carrier frequencies, UE distances, gNB heights, and the limitation to 20 UEs.
The paper should avoid saying the model is “accurate” unless there is measurement validation.

 

7. The paper has many large multi-panel figures near the end. Check if all the figures are necessary. There might be ways to reduce the number of figures. These might confuse the reviewers. You should check whether all are readable in journal format. Each figure should support a specific claim. If a figure is too dense, split it or move supplementary plots to an appendix.

 

8.  The paper needs a full language revision before submission. The writing problems are throughout the paper. You might use grammarly to correct the language. There are issues in grammar, spelling, typos etc. 

 

9. There are terminology inconsistencies. Use one form consistently:

a. ns-3, not “Ns-3,” “ns3,” and “pure_ns-3” interchangeably.

b. Sionna RT, not “SionnaRT.”

c. 5G-LENA, not “5G LENA” or “5G-LENA NR” inconsistently.

d. sionnart should be formatted consistently. If it is a software artifact, define once: sionnart.

e. Use either “ray tracing” as a noun or “ray-traced” as an adjective; avoid inconsistent hyphenation.