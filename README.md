Download Link: https://assignmentchef.com/product/solved-blg242e-experiment6-data-bus-implementation-and-memory-design
<br>
In this experiment, data buses and basic memory are going to be implemented by using three-state buffers.

<strong>You can use any operator/code block in this experiment. Using multiplexer structure is forbidden. You must simulate the all parts and modules.</strong>

<h1>2      Basic Principles</h1>

Buses are frequently used in digital systems in order to reduce the cost of the physical connections. For example, a digital system which consists of <em>N </em>distinct units requires <em>N </em>·(<em>N </em>−1)<em>/</em>2 physical connections to create a fully connected network. Since providing distinct physical lines (wires) for each connection is an expensive approach, sub-set of digital elements communicates through the shared bus in time shared manner. A bus can be implemented as a <em>wired OR </em>circuit by using ICs with open collector outputs or it can be implemented by using 3-state buffers. Abstract design of the <em>wired OR </em>bus is given in the figure below.

Buses can also be implemented by using 3-state buffers. There is no need for a resistor in this design. Output a non-active 3-state buffer will be in high-impedance. There has to be only one active 3-state buffer which runs the bus as an output. An example implementation of a bus by using 3-state buffers is given below.

<h1>3      Part 1</h1>

In this part of the experiment, you should implement an 8-bit bus by using 3-state buffers. The circuit diagram is given in Figure 1.

<strong>Hint: </strong>You must use the three-state buffer as a module. Thus, you must design a three-state buffer module before implementing the circuit.

Figure 1: 8-bit data bus with 2 drivers with 3-state buffers

<h1>4      Part 2</h1>

Figure 2: 8-bit data bus with 2 drivers and 2 readers

In this part of the experiment, you should implement the circuit given in Figure 2. This circuit contains a bus with two distinct outputs and inputs.

<h1>5      Part 3</h1>

In this part, you should implement an 8-bit memory line module. This module should take 8-bit data as input and give 8-bit data as output. Also, the module should take reset, line select, read enable, write enable, and clock inputs for required operations. Required operations are given below.

<ul>

 <li>At the rising edge of the clock signal, the module should store the data value which is given as input when the write enable and line select inputs are high.</li>

 <li>The module should clear the stored data at the falling edge of the reset signal.</li>

 <li>If read enable and line select inputs are high, the output of the module should be the stored data. Otherwise, the output should be high impedance.</li>

</ul>

<h1>6      Part 4</h1>

In this part, you should implement an 8 byte memory module using 8-bit memory line module. 8 byte memory module should take 8-bit data as input and give 8-bit data as output. Also, the module should take 3-bit address, chip select, reset, read enable, write enable, and clock inputs for required operations. Required operations are given below.

<ul>

 <li><strong>Nth </strong>memory line should be selected when the chip select input high. Here, <strong>N </strong>is address number.</li>

 <li>At the rising edge of the clock signal, the selected memory line should store the data, which is given as input, if the write enable input is high.</li>

 <li>The module should clear all stored data in the memory lines at the falling edge of the reset signal.</li>

 <li>The output of the module should be the data of the selected memory line, if read enable input is high.</li>

</ul>

<strong>Hint: </strong>The output of the memory is a bus. Therefore, you do not need to use multiplexer in this experiment.

<h1>7      Part 5</h1>

In this part, you should implement a 32 byte memory module using 8 byte memory module. 32 byte memory module should take 8-bit data as input and give 8-bit data as output. Also, this module should take 5-bit address, reset, read enable, write enable, and clock inputs. 2 bits of the address input should be used for chip selection and rest of 3 bits should be used for selecting line. For instance, if the address input is 00111, zeroth chip (8-byte memory) and its 7th line (0-indexed) should be selected. Your module should be able to perform the operations below.

<ul>

 <li>At the rising edge of the clock signal, the selected memory line should store the data value, which is given as input, if the write enable is high.</li>

 <li>The module should clear the all stored data in the memory modules at the falling edge of the reset signal.</li>

 <li>If read enable is high, the output of the module should be the stored data of the selected memory line.</li>

</ul>

<strong>Example Memory Simulation</strong>

<ul>

 <li>Reset all lines</li>

 <li>Write 25 to Address 30</li>

 <li>Write 15 to Address 20</li>

 <li>Read Address 12</li>

 <li>Write 18 to Address 10</li>

 <li>Read Address 15</li>

 <li>Read Address 30</li>

 <li>Read Address 10</li>

</ul>

<h1>8      Part 6</h1>

In this part, you should implement a 128 byte memory module using 32 byte memory module. 128 byte memory module should take 32-bit data as input and give 32-bit data as output. Also, this module should take address, reset, read enable, write enable and clock inputs. Your module should be able to perform the operations below. • At the rising edge of the clock signal, the selected memory line should store the data value, which is given as input, if the write enable is high.

<ul>

 <li>The module should clear the all stored data in the memory modules at the falling edge of the reset signal. • If read enable is high, the output of the module should be the stored data of the selected memory line.</li>

</ul>

<strong>Hint: </strong>32 byte memory modules have 8-bit inputs and 8-bit outputs. You can use concatenate operation to implement 128 byte memory.