# GPUs

T series.. A series... H series.. TPUs?

There are special formats for Ampere, Turning, and now Hopper GPUs. Hopper GPUs do not support Ampere or Turing formats. This means multiple CUDA kernels and the cuBLASLt integration need to be implemented to make 8-bit (LLMs) work on Hopper GPUs. [source](https://github.com/TimDettmers/bitsandbytes/issues/538)
