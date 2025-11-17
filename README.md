# StorFuzz

## How to Cite
```biblatex
@inproceedings{icse2026-storfuzz,
  title     = {{StorFuzz: Using Data Diversity to Overcome Fuzzing Plateaus}},
  author    = {Weiß, Leon and Holl, Tobias and Borgolte, Kevin},
  booktitle = {Proceedings of the 48th IEEE/ACM International Conference on Software Engineering (ICSE)},
  date      = {2026-04},
  edition   = {48},
  editor    = {Mezini, Mira and Zimmermann, Thomas},
  location  = {Rio de Janeiro, Brazil},
  publisher = {Association for Computing Machinery (ACM)/Institute of Electrical and Electronics Engineers (IEEE)},
  doi       = {10.1145/3744916.3773179}
}
```
<details>
  <summary>How to <code>ß</code></summary>

  LaTeX natively supports unicode and with that the `ß` in Weiß. You may need to use `\usepackage[utf8]{inputenc}`. You can also use `{\ss}` instead of `ß`.

  The correct internationalization of `ß` is `ss`.
</details>

## Source Code

StorFuzz is based on LibAFL revision [bb579e6](https://github.com/AFLplusplus/LibAFL/commit/bb579e624e907b6488f019a6f0bb0634aa0f81da) (v0.13.1), the source code along with usage instructions can be found in [rub-softsec/StorFuzz-LibAFL](https://github.com/rub-softsec/StorFuzz-LibAFL).

## FuzzBench

We include all fuzzers and configurations used in our evaluation as FuzzBench fuzzers: [rub-softsec/StorFuzz-FuzzBench](https://github.com/rub-softsec/StorFuzz-FuzzBench)

The repository includes information on how to replicate the experiments presented in the paper.

### LibAFL fuzzbench fuzzer patch
The fuzzbench fuzzer for LibAFL is based on revision [bb579e6](https://github.com/AFLplusplus/LibAFL/commit/bb579e624e907b6488f019a6f0bb0634aa0f81da). 
The patch applied to the fuzzer can be found in [fuzzbench_stats.patch](./fuzzbench/fuzzers/libafl_stats/fuzzbench_stats.patch) 

### DDFuzz Fuzzer Implementation
The DDFuzz fuzzer for LibAFL is implemented on top of revision [bb579e6](https://github.com/AFLplusplus/LibAFL/commit/bb579e624e907b6488f019a6f0bb0634aa0f81da).
The patch file can be found in [ddfuzz_fuzzer.patch](./fuzzbench/fuzzers/ddfuzz_libafl/ddfuzz_fuzzer.patch) 


### Ablation Study

The configurations used in the ablation study are included as individual fuzzers in [FuzzBench](./fuzzbench/).

#### Reduction Functions
The three alternative reduction functions tested in the ablation study, could be implemented in C as follows:

```c
uint8_t value_reduction_4bits(uint64_t v) {
	uint8_t temp = ((val >> 8) ^ val);
	return ((temp >> 4) ^ temp) & 0xF;
}

uint16_t value_reduction_12bits(uint64_t v) {
	return  (((val & 0xFF00) >> 4) ^ (val & 0xFF)) & 0xFFF;
}

uint16_t value_reduction_16bits(uint64_t v) {
	return  val & 0xFFFF;
}
```

## Additional Data
The following additional tables can be found in [tables.pdf](./artifacts/tables/tables.pdf):

- Corpus sizes of the seed corpus vs. the diversified corpora. *Assessing the Diversity*
- Coverage at different times for median trial starting from the saturated corpus. *Transferring the Diversity: LibAFL*
- Coverage at different times for median trial starting from the saturated corpus. *Transferring the Diversity: WingFuzz*
- Bugs discovered by StorFuzz.
- Edges covered by different coverage guided fuzzers that consider dataflow.

### Additional Coverage Over Time Plots
Here are code coverage over time plots for all FuzzBench benchmarks:

- [Getting to the Plateau](./artifacts/coverage-plots/getting_to_the_plateau/index.md)
- [Breaking out of the Plateau](./artifacts/coverage-plots/breaking_out_of_the_plateau/index.md)
- [Transferring the Diversity: LibAFL](./artifacts/coverage-plots/transferring_the_diversity-libafl/index.md)
- [Transferring the Diversity: WingFuzz](./artifacts/coverage-plots/transferring_the_diversity-wingfuzz/index.md)
- [Transferring the Diversity: WingFuzz (plotted with saturation period)](./artifacts/coverage-plots/transferring_the_diversity-wingfuzz_with_saturation_period/index.md)
- [Ablation Study](./artifacts/coverage-plots/ablation_study/index.md)
- [Starting "from Scratch" (from a Non-Saturated Corpus)](./artifacts/coverage-plots/from_scratch/index.md)


### Seed Corpora & Long-Term Archive
The OSS-Fuzz corpora and the saturated corpora can be found on [Zenodo](https://doi.org/10.5281/zenodo.14979693). This package also includes this repository as a long-term archive.

## Acknowledgements

This work is based on research supported by the Deutsche Forschungsgemeinschaft (DFG, German Research Foundation) under Germany's Excellence Strategy - [EXC 2092 CASA - 390781972](https://casa.rub.de), as well as the Vienna Science and Technology Fund (WWTF) and the City of Vienna [\[Grant ID: 10.47379/ICT19056\]](https://doi.org/10.47379/ICT19056). Any opinions, findings, and conclusions or recommendations expressed in this material are those of the authors and do not necessarily reflect the views of the respective funding agencies.
