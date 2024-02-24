1. Stateful DataFlow Multigraphs: A Data-Centric Model for Performance Portability on Heterogeneous Architectures

- The ubiquity of accelerators in high-performance computing has driven programming complexity beyond the skill-set of the average domain scientist.
- Important to decouple architecture-specific programming paradigms from the underlying scientific computations.
- SDFG, a data-centric intermediate representation that enables __separating program definition from its optimization__.
- Complexity arise in writing portable and performant code due the increase in existing programming specifications like OpenMP, MPI, OpenACC, OpenCL, and CUDA demonstrate the difficult situation in on-node programming.
- Domain Programmer -> (Works in a convenient programming language) -> Compiler Transform the code to SDFG -> Performance Engineer -> (Create program that matches the SDFG)
- SDFG creates a clearly defined separating interface between __Domain Scientist__ and __Performance Engineer__.

TODO: 
1. Write an MPI program.
2. Write a OpenMP program.
3. Write a CUDA program.
4. Write a DaCe program
