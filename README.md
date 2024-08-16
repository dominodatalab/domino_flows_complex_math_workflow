# Domino Flows Complex Workflow Demonstration

This repository demonstrates a complex Domino Flows workflow that showcases parallel task execution, task dependencies, and result aggregation. The workflow is designed to perform various mathematical operations, including addition, subtraction, multiplication, division, modulus, and aggregation of results.

## Files Overview

1. **`add.py`**: A script that adds two numbers.
2. **`subtract.py`**: A script that subtracts one number from another.
3. **`multiply.py`**: A script that multiplies two numbers.
4. **`divide.py`**: A script that divides one number by another (with error handling for division by zero).
5. **`modulus.py`**: A script that calculates the modulus of two numbers.
6. **`aggregate.py`**: A script aggregating the sum, difference, and product results.
7. **`workflow.py`**: The Domino Flows workflow definition that orchestrates the execution of the above scripts.
8. **`run_workflow.py`**: A Python script randomly randomizes the input values and remotely runs the Domino Flows workflow.

## Workflow Overview

### Steps in the Workflow:
1. **Addition and Multiplication (Parallel)**: 
   - The workflow starts by running the addition (`add.py`) and multiplication (`multiply.py`) tasks in parallel.
2. **Subtraction (Dependent on Addition)**:
   - Once the addition task is completed, the subtraction (`subtract.py`) task runs using the sum result.
3. **Division and Modulus (Parallel with Subtraction)**:
   - The division (`divide.py`) and modulus (`modulus.py`) tasks run parallel with the subtraction task, using the original input values.
4. **Aggregation (Dependent on Sum, Difference, and Product)**:
   - Finally, the aggregation task (`aggregate.py`) runs, depending on the results of the sum, difference, and product tasks.

### Outputs:
The workflow returns the following results:
- Sum
- Product
- Difference
- Division Result
- Modulus Result
- Aggregated Result

## Running the Workflow

To demonstrate the workflow, follow these steps:

1. **Randomize Inputs and Run the Workflow**:
   - Run the `run_workflow.py` script, which will randomize the input values `a` and `b`, and execute the Domino Flows workflow with these values.

```bash
python run_workflow.py
```

2. **Observe the Output**:
   - The script will print the randomized values for `a` and `b`, and display the workflow output, including the sum, product, difference, division result, modulus result, and aggregated result.

### Example Command Used in the Script
The script internally executes the following command with randomized values:

```bash
pyDomino Flows run --remote workflow.py complex_math_workflow --a <random_a> --b <random_b>
```

Replace `<random_a>` and `<random_b>` with the randomly generated values for `a` and `b`.

## Summary

This demonstration is an example of leveraging Domino Flows's capabilities to build complex workflows with parallel task execution, dependencies, and result aggregation. 
