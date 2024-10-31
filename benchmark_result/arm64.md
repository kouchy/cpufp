# arm64 CPU benchmark results

## Qualcomm Snapdragon X Elite - X1E80100

Architecture: Oryon-1

Setting: 4 cores @ 3.4Ghz + 8 cores @ 4.0Ghz

For single core:

<pre>
PS C:\Data\cpufp> .\cpufp.exe --thread_pool=[4]
Number Threads: 1
Thread Pool Binding: 4
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| i8mm            | mmla(s32,s8,s8)         | 442.36 GOPS      |
| i8mm            | mmla(u32,u8,u8)         | 434.67 GOPS      |
| i8mm            | mmla(s32,u8,s8)         | 437.35 GOPS      |
| i8mm            | dp4a.vs(s32,s8,u8)      | 520.02 GOPS      |
| i8mm            | dp4a.vs(s32,u8,s8)      | 525.78 GOPS      |
| i8mm            | dp4a.vv(s32,u8,s8)      | 515.6 GOPS       |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 510.91 GOPS      |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 516.89 GOPS      |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 518 GOPS         |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 514.3 GOPS       |
| bf16            | mmla(f32,bf16,bf16)     | 223.53 GFLOPS    |
| bf16            | dp2a.vs(f32,bf16,bf16)  | 256.44 GFLOPS    |
| bf16            | dp2a.vv(f32,bf16,bf16)  | 252.13 GFLOPS    |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 260.4 GFLOPS     |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 259.04 GFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 127.29 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 125.67 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64)    | 65.2 GFLOPS      |
| asimd           | fmla.vv(f64,f64,f64)    | 65.195 GFLOPS    |
----------------------------------------------------------------
</pre>

For 12 cores:

<pre>
PS C:\Data\cpufp> .\cpufp.exe --thread_pool=[0-11]
Number Threads: 12
Thread Pool Binding: 0 1 2 3 4 5 6 7 8 9 10 11
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| i8mm            | mmla(s32,s8,s8)         | 4.3971 TOPS      |
| i8mm            | mmla(u32,u8,u8)         | 4.3813 TOPS      |
| i8mm            | mmla(s32,u8,s8)         | 4.3889 TOPS      |
| i8mm            | dp4a.vs(s32,s8,u8)      | 5.1953 TOPS      |
| i8mm            | dp4a.vs(s32,u8,s8)      | 5.221 TOPS       |
| i8mm            | dp4a.vv(s32,u8,s8)      | 5.209 TOPS       |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 5.2081 TOPS      |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 5.2275 TOPS      |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 5.222 TOPS       |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 5.2146 TOPS      |
| bf16            | mmla(f32,bf16,bf16)     | 2.2578 TFLOPS    |
| bf16            | dp2a.vs(f32,bf16,bf16)  | 2.6124 TFLOPS    |
| bf16            | dp2a.vv(f32,bf16,bf16)  | 2.6172 TFLOPS    |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 2.6051 TFLOPS    |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 2.6035 TFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 1.3028 TFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 1.3032 TFLOPS    |
| asimd           | fmla.vs(f64,f64,f64)    | 654.67 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 654.44 GFLOPS    |
----------------------------------------------------------------
</pre>

## HUAWEI Kunpeng 920 7260

Architecture: Taishan V110

Setting: 2 * 64 cores

For single core:

<pre>
$ ./cpufp --thread_pool=[1]
Number Threads: 1
Thread Pool Binding: 1
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 166.3 GOPS       |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 166.32 GOPS      |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 166.31 GOPS      |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 166.29 GOPS      |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 83.161 GFLOPS    |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 83.151 GFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 41.576 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 41.579 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64)    | 10.395 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 10.394 GFLOPS    |
----------------------------------------------------------------

</pre>

For 32 cores:

<pre>
$ ./cpufp --thread_pool=[0-31]
Number Threads: 32
Thread Pool Binding: 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 5.304 TOPS       |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 5.3108 TOPS      |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 5.307 TOPS       |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 5.3123 TOPS      |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 2.6555 TFLOPS    |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 2.6564 TFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 1.3252 TFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 1.328 TFLOPS     |
| asimd           | fmla.vs(f64,f64,f64)    | 331.95 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 331.98 GFLOPS    |
----------------------------------------------------------------

</pre>

For 64 cores:

<pre>
$ ./cpufp --thread_pool=[0-63]
Number Threads: 64
Thread Pool Binding: 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 51 52 53 54 55 56 57 58 59 60 61 62 63
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 10.601 TOPS      |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 10.586 TOPS      |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 10.587 TOPS      |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 10.593 TOPS      |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 5.2966 TFLOPS    |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 5.2975 TFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 2.6551 TFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 2.6557 TFLOPS    |
| asimd           | fmla.vs(f64,f64,f64)    | 663.98 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 663.73 GFLOPS    |
----------------------------------------------------------------

</pre>

For 128 cores:

<pre>
$ ./cpufp --thread_pool=[0-127]
Number Threads: 128
Thread Pool Binding: 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 51 52 53 54 55 56 57 58 59 60 61 62 63 64 65 66 67 68 69 70 71 72 73 74 75 76 77 78 79 80 81 82 83 84 85 86 87 88 89 90 91 92 93 94 95 96 97 98 99 100 101 102 103 104 105 106 107 108 109 110 111 112 113 114 115 116 117 118 119 120 121 122 123 124 125 126 127
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 20.951 TOPS      |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 20.27 TOPS       |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 19.736 TOPS      |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 16.495 TOPS      |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 10.481 TFLOPS    |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 10.514 TFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 5.1993 TFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 4.117 TFLOPS     |
| asimd           | fmla.vs(f64,f64,f64)    | 1.2754 TFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 1.049 TFLOPS     |
----------------------------------------------------------------

</pre>

## AWS Graviton 3E

Architecture: Neoverse V1

Setting: Virtual 1 Core

For single core:

<pre>
$ ./cpufp --thread_pool=[0]
Number Threads: 1
Thread Pool Binding: 0
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| i8mm            | mmla(s32,s8,s8)         | 332.34 GGOPS     |
| i8mm            | mmla(u32,u8,u8)         | 332.46 GGOPS     |
| i8mm            | mmla(s32,u8,s8)         | 332.46 GGOPS     |
| i8mm            | dp4a.vs(s32,s8,u8)      | 166.23 GGOPS     |
| i8mm            | dp4a.vs(s32,u8,s8)      | 166.17 GGOPS     |
| i8mm            | dp4a.vv(s32,u8,s8)      | 166.14 GGOPS     |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 166.18 GGOPS     |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 166.22 GGOPS     |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 166.22 GGOPS     |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 166.22 GGOPS     |
| bf16            | mmla(f32,bf16,bf16)     | 166.18 GGFLOPS   |
| bf16            | dp2a.vs(f32,bf16,bf16)  | 83.085 GGFLOPS   |
| bf16            | dp2a.vv(f32,bf16,bf16)  | 83.111 GGFLOPS   |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 83.105 GGFLOPS   |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 83.113 GGFLOPS   |
| asimd           | fmla.vs(f32,f32,f32)    | 41.549 GGFLOPS   |
| asimd           | fmla.vv(f32,f32,f32)    | 41.542 GGFLOPS   |
| asimd           | fmla.vs(f64,f64,f64)    | 35.96 GGFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 20.779 GGFLOPS   |
----------------------------------------------------------------
</pre>

## Broadcom BCM2711(RaspBerry Pi 4)

Setting: 4 Cortex-A72 Cores

For single core:

<pre>
$ ./cpufp --thread_pool=[0]
Number Threads: 1
Thread Pool Binding: 0
-------------------------------------------------------------
| Instruction Set | Core Computation     | Peak Performance |
| asimd           | fmla.vs(f32,f32,f32) | 11.958 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32) | 11.958 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64) | 5.9792 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64) | 5.9792 GFLOPS    |
-------------------------------------------------------------
</pre>

For 4 cores:

<pre>
$ ./cpufp --thread_pool=[0-3]
Number Threads: 4
Thread Pool Binding: 0 1 2 3
-------------------------------------------------------------
| Instruction Set | Core Computation     | Peak Performance |
| asimd           | fmla.vs(f32,f32,f32) | 47.883 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32) | 47.88 GFLOPS     |
| asimd           | fmla.vs(f64,f64,f64) | 23.933 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64) | 23.943 GFLOPS    |
-------------------------------------------------------------
</pre>

## Broadcom BCM2712(RaspBerry Pi 5)

Setting: 4 Cortex-A76 Cores

For single core:

<pre>
$ ./cpufp --thread_pool=[0]
Number Threads: 1
Thread Pool Binding: 0
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 153.48 GOPS      |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 153.48 GOPS      |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 153.47 GOPS      |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 153.48 GOPS      |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 76.738 GFLOPS    |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 76.738 GFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 38.369 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 38.369 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64)    | 19.185 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 19.185 GFLOPS    |
----------------------------------------------------------------
</pre>

For 4 cores:

<pre>
$ ./cpufp --thread_pool=[0-3]
Number Threads: 4
Thread Pool Binding: 0 1 2 3
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 613.79 GOPS      |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 614.02 GOPS      |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 613.98 GOPS      |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 613.99 GOPS      |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 306.88 GFLOPS    |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 306.98 GFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 153.48 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 153.5 GFLOPS     |
| asimd           | fmla.vs(f64,f64,f64)    | 74.513 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 76.751 GFLOPS    |
----------------------------------------------------------------
</pre>

## RockChip RK3588

Setting: 4 Cortex-A76(big) Cores + 4 Cortex-A55(Little) Cores

For single Little core:

<pre>
$ ./cpufp --thread_pool=[0]
Number Threads: 1
Thread Pool Binding: 0
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 58.379 GOPS      |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 58.371 GOPS      |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 58.369 GOPS      |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 58.382 GOPS      |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 29.193 GFLOPS    |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 29.192 GFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 14.593 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 14.596 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64)    | 7.2971 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 7.2972 GFLOPS    |
----------------------------------------------------------------
</pre>

For 4 Little cores:

<pre>
$ ./cpufp --thread_pool=[0-3]
Number Threads: 4
Thread Pool Binding: 0 1 2 3
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 233.08 GOPS      |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 233.05 GOPS      |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 233.06 GOPS      |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 233.05 GOPS      |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 116.54 GFLOPS    |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 116.51 GFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 58.261 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 58.258 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64)    | 29.13 GFLOPS     |
| asimd           | fmla.vv(f64,f64,f64)    | 29.126 GFLOPS    |
----------------------------------------------------------------
</pre>

For single big core:

<pre>
$ ./cpufp --thread_pool=[4]
Number Threads: 1
Thread Pool Binding: 4
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 152.1 GOPS       |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 152.1 GOPS       |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 152.06 GOPS      |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 152.08 GOPS      |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 76.022 GFLOPS    |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 76.027 GFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 38.012 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 38.008 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64)    | 19.004 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 19.004 GFLOPS    |
----------------------------------------------------------------
</pre>

For 4 big cores:

<pre>
$ ./cpufp --thread_pool=[4-7]
Number Threads: 4
Thread Pool Binding: 4 5 6 7
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 601.71 GOPS      |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 602.2 GOPS       |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 602.22 GOPS      |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 602.2 GOPS       |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 300.97 GFLOPS    |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 300.93 GFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 149.79 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 150.15 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64)    | 75.222 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 75.215 GFLOPS    |
----------------------------------------------------------------
</pre>

## Rockchip RK3399

Setting: 2 Cortex-A72(big) Cores + 4 Cortex-A53(Little) Cores

For single Little core:

<pre>
$ ./cpufp --thread_pool=[0]
Number Threads: 1
Thread Pool Binding: 0
-------------------------------------------------------------
| Instruction Set | Core Computation     | Peak Performance |
| asimd           | fmla.vs(f32,f32,f32) | 11.255 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32) | 11.255 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64) | 5.6275 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64) | 5.6277 GFLOPS    |
-------------------------------------------------------------
</pre>

For 4 Little cores:

<pre>
$ ./cpufp --thread_pool=[0-3]
Number Threads: 4
Thread Pool Binding: 0 1 2 3
-------------------------------------------------------------
| Instruction Set | Core Computation     | Peak Performance |
| asimd           | fmla.vs(f32,f32,f32) | 45.029 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32) | 45.027 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64) | 22.509 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64) | 22.513 GFLOPS    |
-------------------------------------------------------------
</pre>

For single big core:

<pre>
$ ./cpufp --thread_pool=[4]
Number Threads: 1
Thread Pool Binding: 4
-------------------------------------------------------------
| Instruction Set | Core Computation     | Peak Performance |
| asimd           | fmla.vs(f32,f32,f32) | 14.348 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32) | 14.348 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64) | 7.1744 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64) | 7.1743 GFLOPS    |
-------------------------------------------------------------
</pre>

For 2 big cores:

<pre>
$ ./cpufp --thread_pool=[4,5]
Number Threads: 2
Thread Pool Binding: 4 5
-------------------------------------------------------------
| Instruction Set | Core Computation     | Peak Performance |
| asimd           | fmla.vs(f32,f32,f32) | 28.698 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32) | 28.698 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64) | 14.349 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64) | 14.347 GFLOPS    |
-------------------------------------------------------------
</pre>

## Phytium D2000/8

Setting: 8 FTC663 Cores

For single core:

<pre>
$ ./cpufp --thread_pool=[0]
Number Threads: 1
Thread Pool Binding: 0
-------------------------------------------------------------
| Instruction Set | Core Computation     | Peak Performance |
| asimd           | fmla.vs(f32,f32,f32) | 18.376 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32) | 18.375 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64) | 9.1877 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64) | 9.1891 GFLOPS    |
-------------------------------------------------------------
</pre>

For 4 cores:

<pre>
$ ./cpufp --thread_pool=[0-3]
Number Threads: 4
Thread Pool Binding: 0 1 2 3
-------------------------------------------------------------
| Instruction Set | Core Computation     | Peak Performance |
| asimd           | fmla.vs(f32,f32,f32) | 73.51 GFLOPS     |
| asimd           | fmla.vv(f32,f32,f32) | 73.51 GFLOPS     |
| asimd           | fmla.vs(f64,f64,f64) | 36.755 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64) | 36.747 GFLOPS    |
-------------------------------------------------------------
</pre>

## Apple Silicon M1 Ultra

For 1x e-core (Icestorm):

<pre>
$ ./cpufp --thread_pool=[0]
Number Threads: 1
Thread Pool Binding: 0
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 131.74 GOPS      |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 131.83 GOPS      |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 131.72 GOPS      |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 131.81 GOPS      |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 65.88 GFLOPS     |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 65.886 GFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 32.892 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 32.953 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64)    | 16.452 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 16.476 GFLOPS    |
----------------------------------------------------------------
</pre>

For 4x e-core (Icestorm):

<pre>
$ ./cpufp --thread_pool=[0,1,10,11]
Number Threads: 4
Thread Pool Binding: 0 1 10 11
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 526.63 GOPS      |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 526.62 GOPS      |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 526.36 GOPS      |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 526.64 GOPS      |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 263.3 GFLOPS     |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 263.36 GFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 131.65 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 131.66 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64)    | 65.815 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 65.816 GFLOPS    |
----------------------------------------------------------------
</pre>

For 1x p-core (Firestorm):

<pre>
$ ./cpufp --thread_pool=[2]
Number Threads: 1
Thread Pool Binding: 2
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 411.79 GOPS      |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 412.35 GOPS      |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 412.47 GOPS      |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 411.79 GOPS      |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 206.26 GFLOPS    |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 206.25 GFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 103.14 GFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 103.12 GFLOPS    |
| asimd           | fmla.vs(f64,f64,f64)    | 51.562 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 51.518 GFLOPS    |
----------------------------------------------------------------
</pre>

For 16x p-core (Firestorm):

<pre>
$ ./cpufp --thread_pool=[2-9,12-19]
Number Threads: 16
Thread Pool Binding: 2 3 4 5 6 7 8 9 12 13 14 15 16 17 18 19
----------------------------------------------------------------
| Instruction Set | Core Computation        | Peak Performance |
| asimd_dp        | dp4a.vs(s32,s8,s8)      | 6.2011 TOPS      |
| asimd_dp        | dp4a.vv(s32,s8,s8)      | 6.2024 TOPS      |
| asimd_dp        | dp4a.vs(u32,u8,u8)      | 6.2013 TOPS      |
| asimd_dp        | dp4a.vv(u32,u8,u8)      | 6.2026 TOPS      |
| asimd_hp        | fmla.vs(fp16,fp16,fp16) | 3.1016 TFLOPS    |
| asimd_hp        | fmla.vv(fp16,fp16,fp16) | 3.1012 TFLOPS    |
| asimd           | fmla.vs(f32,f32,f32)    | 1.5507 TFLOPS    |
| asimd           | fmla.vv(f32,f32,f32)    | 1.5507 TFLOPS    |
| asimd           | fmla.vs(f64,f64,f64)    | 774.91 GFLOPS    |
| asimd           | fmla.vv(f64,f64,f64)    | 775.4 GFLOPS     |
----------------------------------------------------------------
</pre>
