# QOSF Mentorsip Program Screenning Task 2

## Libraries Use
* `pennylane`
* `qiskit`
* plugin of pennylane for qiskit - `pennylane-qiskit`
* `numpy`

## Steps

### 1. Create Vanilla Circuit
    * Use H, X and CX quantum gates
    * Convert the quantum gates to restricted set of quantum gates
### 2. Create Parameteized Circuit
    * Set Initial state to |00>
    * set All angles to 0
    * train using gradient descent optimizer from pennylane
### 3. Figure out approach for producing state $|01\rangle$ + $|10\rangle$ and not $|01\rangle$ - $|10\rangle$ 
#### Steps that we can take to distinguish +i, -i phases i.e. (|0> + i|1>) and (|0> - i|1>)
- Change the measurement basis to X@Y (PauliX measurement on qubit_0 and PauliY on qubit_1)
#### Steps that we can take to distinguish +1, -1 phases i.e. (|0> + |1>) and (|0> - |1>)
- Change the measurement basis to X@X (PauliX measurement on both qubit_0 and qubit_1)
#### To combine both results to distinguish +1 phase from other phases
- Create a quantum node collection for 2 nodes of the same circuit
- Alter the gradient function
    - cost = |X@Y|-X@X + gradient(prob)
### 4. Test final approach for different number of measurements 1, 10, 100, 1000

