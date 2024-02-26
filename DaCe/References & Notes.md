## 1.
Stateful DataFlow Multigraphs: A Data-Centric Model for Performance Portability on Heterogeneous Architectures

- The ubiquity of accelerators in high-performance computing has driven programming complexity beyond the skill-set of the average domain scientist.
- Important to decouple architecture-specific programming paradigms from the underlying scientific computations.
- SDFG, a data-centric intermediate representation that enables __separating program definition from its optimization__.
- Complexity arise in writing portable and performant code due the increase in existing programming specifications like OpenMP, MPI, OpenACC, OpenCL, and CUDA demonstrate the difficult situation in on-node programming.
- Domain Programmer -> (Works in a convenient programming language) -> Compiler Transform the code to SDFG -> Performance Engineer -> (Create program that matches the SDFG)
- SDFG creates a clearly defined separating interface between __Domain Scientist__ and __Performance Engineer__.

####  Dataflow VS Data-centric Parallel Programming

- In dataflow model, execution is stateless.
- Control-centric programs revolve around statements that are executed in order. 
- Data-centric parallel programming promotes the use of stateful dataflow. (Execution order depends first on data dependencies, but also on a global execution state)

##### Data-centric Parallel Programming

A data-centric model combines the following concepts:
1. Separate Containers from Computation: 
2. Dataflow
3. States
4. Coarsening

#### DaCe - Python Interface

- DaCe programs exist as decorated, strongly-typed functions.
- The Python interface contains primitives such as _map_ and _reduce_.
##### Domain Scientist Interface
- Support __numpy operators__ and __functions__ and also can __explicitly specify dataflow__.
- User can create new dataflow implementations using decorated functions (`dace.replaces('numpy.conj')`) that describe the SDFG.

__Tasklets__:
- If the programmer does not use predefined operators, dataflow __intrinsics__ can be explicitly defined separately from code, in constructs which they call Tasklets.
- Tasklet functions cannot access data unless it was explicitly moved in or out using pre-declared operators (<<, >>) on arrays.

__Memlets__:
- Data movement operations (memlets) can be versatile.

#### SDFG

- SDFGs are _directed acyclic multigraphs_.
	- Node represent: __Containers__ or __Computation__
	- Edge represent: __Data Movements__ (Memlets)

TODO: 
1. Write an MPI program.
2. Write a OpenMP program.
3. Write a CUDA program.
4. Write a DaCe program
