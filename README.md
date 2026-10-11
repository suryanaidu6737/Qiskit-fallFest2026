# IBM Quantum - Qiskit Fall Fest 2026
**Vishnu Institute of Technology**

This repository contains solutions, quantum circuit implementations, and hardware execution results for all four challenges of the Qiskit Fall Fest 2026[cite: 1, 3, 4, 5].

---

## Environment Setup & Installation

### 1. Prerequisites
Ensure you have Python 3.10 or newer installed.

### 2. Install Required Dependencies
Run the following command in your terminal to install Qiskit, the IBM Quantum Runtime client, and plotting tools[cite: 2]:

pip install --upgrade qiskit qiskit-ibm-runtime matplotlib pylatexenc

### 3. Save IBM Quantum Platform Credentials
Run this script once in Python to save your credentials locally[cite: 2]:

from qiskit_ibm_runtime import QiskitRuntimeService

QiskitRuntimeService.save_account(
    channel="ibm_quantum_platform",
    instance="<YOUR_CRN_INSTANCE_STRING>",
    token="<YOUR_IBM_QUANTUM_API_TOKEN>",
    overwrite=True,
    set_as_default=True
)

---

## How to Run the Notebooks

1. Clone this repository:
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>

2. Start Jupyter Lab:
jupyter lab

3. Standard Execution Pipeline used in each challenge notebook:
* Build Circuits: Construct circuits using standard gates (H, X, CX, Ry) and measurement registers[cite: 1, 2, 4, 5].
* Connect Backend: Initialize QiskitRuntimeService() and select the least busy QPU via service.least_busy(operational=True, simulator=False)[cite: 2].
* Transpile: Optimize for device topology using generate_preset_pass_manager(target=backend.target, optimization_level=3)[cite: 2].
* Run: Execute using SamplerV2(mode=backend) with shots=100[cite: 1, 3, 4, 5].
* Visualize: Display measurement distributions with plot_histogram()[cite: 1, 2, 3, 4, 5].

---

## Challenge 1: Predict the Output

### Problem Statement
A quantum circuit can produce different measurement outcomes depending on the gates applied to a qubit[cite: 4].
Your task is to predict the output of simple quantum circuits before executing them and then compare your prediction with the actual measurement results[cite: 4].

### Tasks
1. Create a single-qubit quantum circuit[cite: 4].
2. Prepare the qubit in the initial state |0>[cite: 4].
3. Construct and investigate the following circuits[cite: 4]:
   * Circuit A: Apply an X gate and measure[cite: 4].
   * Circuit B: Apply two X gates and measure[cite: 4].
   * Circuit C: Apply an H gate and measure[cite: 4].
4. Before executing each circuit, predict the expected measurement outcome[cite: 4].
5. Execute each circuit for 100 shots[cite: 4].
6. Record the measurement results[cite: 4].
7. Compare your predictions with the actual results[cite: 4].
8. Display the results using a histogram[cite: 4].

### Think Before You Run
Before executing the circuits, predict[cite: 4]:
* What will happen after applying one X gate[cite: 4]?
* What will happen after applying two X gates[cite: 4]?
* What do you expect after applying an H gate[cite: 4]?
* Will Circuit C always produce the same measurement result[cite: 4]?

### Design Constraints
* Use exactly 1 qubit[cite: 4].
* Include measurement[cite: 4].
* Use only the gates introduced in the workshop[cite: 4].
* Be created and executed using Qiskit[cite: 4].
* Use 100 shots for each experiment[cite: 4].

### Submission Deliverables
* The three quantum circuits[cite: 4].
* Your prediction for each circuit[cite: 4].
* Measurement results for 100 shots[cite: 4].
* Histograms of the results[cite: 4].
* A short comparison between your predictions and the actual results[cite: 4].

---

## Challenge 2: Make the Quantum Coin Biased

### Problem Statement
A Hadamard gate creates an equal superposition of |0> and |1>, producing a result similar to a fair quantum coin[cite: 5]. But can you control the measurement probabilities[cite: 5]? Your task is to modify a single-qubit circuit so that the measurement outcomes are not equally distributed[cite: 5].

### Tasks
1. Create a single-qubit quantum circuit[cite: 5].
2. Start with the qubit in |0>[cite: 5].
3. Apply quantum gates to create a state whose measurement probabilities for 0 and 1 are different[cite: 5].
4. Measure the qubit[cite: 5].
5. Execute the circuit for 100 shots[cite: 5].
6. Observe the number of 0 and 1 outcomes[cite: 5].
7. Display the results using a histogram[cite: 5].
8. Try to create different degrees of bias[cite: 5].

### Think Before You Run
Before executing your circuit, predict[cite: 5]:
* Will 0 or 1 occur more frequently[cite: 5]?
* Approximately what percentage of the measurements will produce each outcome[cite: 5]?
* What happens if you change the gates in your circuit[cite: 5]?

### Design Constraints
* Use exactly 1 qubit[cite: 5].
* Include measurement[cite: 5].
* Use no more than 4 quantum gates before measurement[cite: 5].
* Be created and executed using Qiskit[cite: 5].
* Use 100 shots[cite: 5].

### Bonus Challenge
Try to design two different circuits[cite: 5]:
* One where 0 occurs more frequently[cite: 5].
* One where 1 occurs more frequently[cite: 5].
* Compare their histograms[cite: 5].

### Submission Deliverables
* Your quantum circuit[cite: 5].
* Your predicted probabilities[cite: 5].
* Measurement results for 100 shots[cite: 5].
* Histogram of the results[cite: 5].
* A short explanation of how your gates changed the measurement distribution[cite: 5].
* Challenge Question: How can quantum gates change the probability of obtaining 0 or 1 when a qubit is measured[cite: 5]?

---

## Challenge 3: Can You Change the Correlation?

### Problem Statement
Two qubits can be prepared in a state where their measurement outcomes are strongly correlated[cite: 1]. Your task is to modify a two-qubit circuit and investigate whether you can change the relationship between the two measurement outcomes[cite: 1].

### Tasks
1. Create a two-qubit quantum circuit[cite: 1].
2. Start from the Bell-state circuit demonstrated during the workshop[cite: 1].
3. Add or modify one quantum gate[cite: 1].
4. Measure both qubits[cite: 1].
5. Execute the circuit for 100 shots[cite: 1].
6. Observe the measurement results[cite: 1].
7. Display the results using a histogram[cite: 1].
8. Compare the results with the original circuit[cite: 1].
9. Explain how the modification changed the measurement outcomes[cite: 1].

### Think Before You Run
Before executing your modified circuit, predict[cite: 1]:
* Which outcomes do you expect[cite: 1]?
* Will the two qubits still produce the same outcomes[cite: 1]?
* Will 00 and 11 dominate[cite: 1]?
* Could 01 and 10 become more frequent[cite: 1]?

### Design Constraints
* Use exactly 2 qubits[cite: 1].
* Measure both qubits[cite: 1].
* Start from the Bell-state circuit[cite: 1].
* Add or modify only one quantum gate[cite: 1].
* Use no more than 4 quantum gates before measurement[cite: 1].
* Be created and executed using Qiskit[cite: 1].
* Use 100 shots[cite: 1].

### Submission Deliverables
* Original circuit[cite: 1].
* Modified circuit[cite: 1].
* Prediction before execution[cite: 1].
* Measurement results for both circuits[cite: 1].
* Histograms[cite: 1].
* A short explanation of the observed change[cite: 1].

---

## Challenge 4: Quantum Correlation Switch

### Problem Statement
In Challenge 3, how a quantum circuit can produce correlated outcomes is investigated[cite: 3]. Now, design a circuit that switches between correlated and opposite measurement outcomes[cite: 3]. Your goal is to create two different two-qubit behaviors using only a small number of quantum gates[cite: 3].

### Tasks
* Part A - Correlated Outcomes: Design a two-qubit circuit in which the measurement results are predominantly 00 and 11[cite: 3]. Run the circuit for 100 shots and record the results[cite: 3].
* Part B - Opposite Outcomes: Modify your circuit so that the measurement results are predominantly 01 and 10[cite: 3]. Run the modified circuit for 100 shots and record the results[cite: 3].
* Part C - Compare: Compare the two circuits using histograms[cite: 3]. Explain[cite: 3]:
  * Which outcomes are dominant in Part A[cite: 3]?
  * Which outcomes are dominant in Part B[cite: 3]?
  * What changed between the two circuits[cite: 3]?
  * Why did the measurement relationship change[cite: 3]?

### Think Before You Run
Before executing your circuits, predict[cite: 3]:
* Which outcomes should dominate in Part A[cite: 3]?
* Which outcomes should dominate in Part B[cite: 3]?
* Will all four possible outcomes appear[cite: 3]?
* Why might some outcomes be much more frequent than others[cite: 3]?

### Design Constraints
* Use exactly 2 qubits[cite: 3].
* Measure both qubits[cite: 3].
* Use no more than 4 quantum gates before measurement
