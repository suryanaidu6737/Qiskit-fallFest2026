# IBM Quantum - Qiskit Fall Fest 2026
**Vishnu Institute of Technology**

This repository contains solutions and quantum circuit implementations for the four challenges of the Qiskit Fall Fest 2026.

---

## Challenge 1: Predict the Output

### Problem Statement
A quantum circuit can produce different measurement outcomes depending on the gates applied to a qubit.
The task is to predict the output of simple quantum circuits before executing them and then compare the prediction with the actual measurement results.

### Tasks
1. Create a single-qubit quantum circuit.
2. Prepare the qubit in the initial state $\vert{}0\rangle$.
3. Construct and investigate the following circuits:
   - **Circuit A:** Apply an $X$ gate and measure.
   - **Circuit B:** Apply two $X$ gates and measure.
   - **Circuit C:** Apply an $H$ gate and measure.
4. Predict the expected measurement outcome before execution.
5. Execute each circuit for 100 shots.
6. Record measurement results.
7. Compare predictions with actual results.
8. Display results using a histogram.

### Design Constraints
- Use exactly 1 qubit.
- Include measurement.
- Use only gates introduced during the workshop.
- Created and executed using Qiskit.
- Use 100 shots for each experiment.

### Submission Deliverables
- The three quantum circuits.
- Prediction for each circuit.
- Measurement results for 100 shots.
- Histograms of the results.
- A short comparison between predictions and actual results.

---

## Challenge 2: Make the Quantum Coin Biased

### Problem Statement
A Hadamard gate creates an equal superposition of $\vert{}0\rangle$ and $\vert{}1\rangle$, producing a result similar to a fair quantum coin. The task is to modify a single-qubit circuit so that the measurement outcomes are not equally distributed.

### Tasks
1. Create a single-qubit quantum circuit.
2. Start with the qubit in $\vert{}0\rangle$.
3. Apply quantum gates to create a state whose measurement probabilities for 0 and 1 are different.
4. Measure the qubit.
5. Execute the circuit for 100 shots.
6. Observe the number of 0 and 1 outcomes.
7. Display results using a histogram.
8. Try to create different degrees of bias.

### Design Constraints
- Use exactly 1 qubit.
- Include measurement.
- Use no more than 4 quantum gates before measurement.
- Created and executed using Qiskit.
- Use 100 shots.

### Submission Deliverables
- Quantum circuit.
- Predicted probabilities.
- Measurement results for 100 shots.
- Histogram of the results.
- A short explanation of how gates changed the measurement distribution.
- **Challenge Question:** How can quantum gates change the probability of obtaining 0 or 1 when a qubit is measured?

---

## Challenge 3: Can you change the correlation?

### Problem Statement
Two qubits can be prepared in a state where their measurement outcomes are strongly correlated. The task is to modify a two-qubit circuit and investigate whether you can change the relationship between the two measurement outcomes.

### Tasks
1. Create a two-qubit quantum circuit.
2. Start from the Bell-state circuit demonstrated during the workshop.
3. Add or modify one quantum gate.
4. Measure both qubits.
5. Execute the circuit for 100 shots.
6. Observe measurement results.
7. Display results using a histogram.
8. Compare results with the original circuit.
9. Explain how the modification changed the measurement outcomes.

### Design Constraints
- Use exactly 2 qubits.
- Measure both qubits.
- Start from the Bell-state circuit.
- Add or modify only one quantum gate.
- Use no more than 4 quantum gates before measurement.
- Created and executed using Qiskit.
- Use 100 shots.

### Submission Deliverables
- Original circuit.
- Modified circuit.
- Prediction before execution.
- Measurement results for both circuits.
- Histograms.
- A short explanation of the observed change.

---

## Challenge 4: Quantum Correlation Switch

### Problem Statement
In Challenge 3, how a quantum circuit can produce correlated outcomes is investigated. Now, design a circuit that switches between correlated and opposite measurement outcomes using only a small number of quantum gates.

### Tasks
- **Part A - Correlated Outcomes:** Design a two-qubit circuit where measurement results are predominantly `00` and `11`. Run for 100 shots and record results.
- **Part B - Opposite Outcomes:** Modify the circuit so measurement results are predominantly `01` and `10`. Run for 100 shots and record results.
- **Part C - Compare:** Compare both circuits using histograms and explain the dominant outcomes and mechanism of change.

### Design Constraints
- Use exactly 2 qubits.
- Measure both qubits.
- Use no more than 4 quantum gates before measurement.
- Use only gates introduced during the workshop.
- Created and executed using Qiskit.
- Use 100 shots for each experiment.

### Submission Deliverables
- Circuit for Part A.
- Circuit for Part B.
- Predictions for both circuits.
- Measurement results for 100 shots.
- Histograms for both circuits.
- A comparison of the two experiments.
- A short explanation of how the circuit produces the different correlations.

  Setup & Running the Notebooks
Clone the repo:

Bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
Install dependencies:

Bash
pip install qiskit qiskit-ibm-runtime matplotlib pylatexenc
Authenticate IBM Quantum:

Python
from qiskit_ibm_runtime import QiskitRuntimeService
QiskitRuntimeService.save_account(
    channel="ibm_quantum_platform",
    token="YOUR_IBM_QUANTUM_TOKEN",
    instance="YOUR_CRN_OR_INSTANCE",
    overwrite=True
)

