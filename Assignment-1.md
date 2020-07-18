### What are Channels and Kernels (according to EVA)?

#### Channels:

Channels are collections of similar features. For example: 
- in a RGB image, there are three channels(not a very apt example).

#### Kernels: 

- Kernels are feature extractors. 

### Why should we only (well mostly) use 3x3 Kernels?

There are couple of reasons for using a 3x3 Kernels:

- Any other kernel can be implemented with a 3x3 kernel. 
  - For example, to implement a 5x5 kernel we can have 2 3x3 kernels.
  - For example, to implement a 7x7 kernel we can have 3 3x3 kernels.
- They have less number of parameters.
  - Number of parameters for 5x5 = 25, 2x3x3 = 18
  - Number of parameters for 7x7 = 49, 3x3x3 = 27
  - Number of parameters for 9x9 = 81, 4x3x3 = 36
- Also when we use multiple 3x3 kernel instead of a bigger kernel, we also get to transition stages. 
  - for example, 7x7 can be implemented by 7x7(input) -> 3x3(conv) --> 5x5(output) --> 3x3(conv) --> 3x3(output) -> 3x3(conv) --> 1x1(output)

- There are faster implementations of 3x3 kernels compared to other sizes.

### How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)

To reach **1x1** from **199x199** we have to do **3x3** convolutions **99** times

See the calculations below:

Input   | Conv      |   Output
--- | --- | ---
199x199 | conv(3x3) |	197x197
197x197 | conv(3x3) |	195x195
195x195 | conv(3x3) |	193x193
193x193 | conv(3x3) |	191x191
191x191 | conv(3x3) |	189x189
189x189 | conv(3x3) |	187x187
187x187 | conv(3x3) |	185x185
185x185 | conv(3x3) |	183x183
183x183 | conv(3x3) |	181x181
181x181 | conv(3x3) |	179x179
179x179 | conv(3x3) |	177x177
177x177 | conv(3x3) |	175x175
175x175 | conv(3x3) |	173x173
173x173 | conv(3x3) |	171x171
171x171 | conv(3x3) |	169x169
169x169 | conv(3x3) |	167x167
167x167 | conv(3x3) |	165x165
165x165 | conv(3x3) |	163x163
163x163 | conv(3x3) |	161x161
161x161 | conv(3x3) |	159x159
159x159 | conv(3x3) |	157x157
157x157 | conv(3x3) |	155x155
155x155 | conv(3x3) |	153x153
153x153 | conv(3x3) |	151x151
151x151 | conv(3x3) |	149x149
149x149 | conv(3x3) |	147x147
147x147 | conv(3x3) |	145x145
145x145 | conv(3x3) |	143x143
143x143 | conv(3x3) |	141x141
141x141 | conv(3x3) |	139x139
139x139 | conv(3x3) |	137x137
137x137 | conv(3x3) |	135x135
135x135 | conv(3x3) |	133x133
133x133 | conv(3x3) |	131x131
131x131 | conv(3x3) |	129x129
129x129 | conv(3x3) |	127x127
127x127 | conv(3x3) |	125x125
125x125 | conv(3x3) |	123x123
123x123 | conv(3x3) |	121x121
121x121 | conv(3x3) |	119x119
119x119 | conv(3x3) |	117x117
117x117 | conv(3x3) |	115x115
115x115 | conv(3x3) |	113x113
113x113 | conv(3x3) |	111x111
111x111 | conv(3x3) |	109x109
109x109 | conv(3x3) |	107x107
107x107 | conv(3x3) |	105x105
105x105 | conv(3x3) |	103x103
103x103 | conv(3x3) |	101x101
101x101 | conv(3x3) |	99x99
99x99   | conv(3x3) |	97x97
97x97   | conv(3x3) |	95x95
95x95   | conv(3x3) |	93x93
93x93   | conv(3x3) |	91x91
91x91   | conv(3x3) |	89x89
89x89   | conv(3x3) |	87x87
87x87   | conv(3x3) |	85x85
85x85   | conv(3x3) |	83x83
83x83   | conv(3x3) |	81x81
81x81   | conv(3x3) |	79x79
79x79   | conv(3x3) |	77x77
77x77   | conv(3x3) |	75x75
75x75   | conv(3x3) |	73x73
73x73   | conv(3x3) |	71x71
71x71   | conv(3x3) |	69x69
69x69   | conv(3x3) |	67x67
67x67   | conv(3x3) |	65x65
65x65   | conv(3x3) |	63x63
63x63   | conv(3x3) |	61x61
61x61   | conv(3x3) |	59x59
59x59   | conv(3x3) |	57x57
57x57   | conv(3x3) |	55x55
55x55   | conv(3x3) |	53x53
53x53   | conv(3x3) |	51x51
51x51   | conv(3x3) |	49x49
49x49   | conv(3x3) |	47x47
47x47   | conv(3x3) |	45x45
45x45   | conv(3x3) |	43x43
43x43   | conv(3x3) |	41x41
41x41   | conv(3x3) |	39x39
39x39   | conv(3x3) |	37x37
37x37   | conv(3x3) |	35x35
35x35   | conv(3x3) |	33x33
33x33   | conv(3x3) |	31x31
31x31   | conv(3x3) |	29x29
29x29   | conv(3x3) |	27x27
27x27   | conv(3x3) |	25x25
25x25   | conv(3x3) |	23x23
23x23   | conv(3x3) |	21x21
21x21   | conv(3x3) |	19x19
19x19   | conv(3x3) |	17x17
17x17   | conv(3x3) |	15x15
15x15   | conv(3x3) |	13x13
13x13   | conv(3x3) |	11x11
11x11   | conv(3x3) |	9x9
9x9     | conv(3x3) |	7x7
7x7     | conv(3x3) |	5x5
5x5     | conv(3x3) |	3x3
3x3     | conv(3x3) |	1x1

### How are kernels initialized

- Kernel initialization was done randomly for a long time in the history of DNNs. But recently, it has been proved, that initialization can have a impact on convergence of a neural network. 
- The values should not be a very **small values(vanishing gradients)** or **very large values(exploding gradients)**.
- [Xavier initialization](https://pytorch.org/docs/stable/nn.init.html#torch.nn.init.xavier_uniform_) is one of the techniques that is popularly used for initialization.

### What happens during the training of DNNs

There are a lot of things that happen during training DNNs. I have tried to explain that in this answer very concisely. 

We start with initializing the parameters of the network(Kernel initialization above). We also select an appropriate optimization algorithm. Once this is done, we iteratively, forward propagate the input and compute the error, followed by gradients of the error with respect to kernels(BPTT). Then we update each parameter. 
