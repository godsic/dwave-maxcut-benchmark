# dwave-maxcut-benchmark
An Example of Simple Max-Cut Problem Solved with D-Wave Leap Quantum Cloud Service

## Prerequisites

- Python 3.5+ and [pipenv](https://docs.pipenv.org/);
- clone this repo
    ```bash
    git clone https://github.com/godsic/dwave-maxcut-benchmark.git && cd dwave-maxcut-benchmark
    ```
- configure Python environment with [D-Wave Ocean SDK](https://docs.ocean.dwavesys.com/en/stable/) by running the following command:
    ```bash
    pipenv install
    ```
- register at [D-Wave Leap](https://cloud.dwavesys.com/leap/) and obtain corresponding API key;
- configure environment with [dwave CLI](https://docs.ocean.dwavesys.com/en/stable/docs_cli.html#cli-example-config)  providing the API key when asked:
    ```bash
    dwave config create
    ```

## How to run

Simply execute
```bash
pipenv run ./maxcut.py
```
and will print obtained solutions, their energies, frequencies during sampling and detailed QPU timings.

## Results

The following results are obtained with `Advantage_system1.1`:

### Problem #1

$$
Q_{QUBO} = \begin{bmatrix}
22 & -8 & 2 & 11\\
& 0 & 11 & -3\\
& & 22 & -8\\
& & & 0
\end{bmatrix}
$$

#### Solution
```bash
   0  1  2  3 energy num_oc. chain_.
0  0  1  0  1   -3.0       5     0.0
1  0  0  0  1    0.0       2     0.0
2  0  0  0  0    0.0       3     0.0
['BINARY', 3 rows, 10 samples, 4 variables]
```
#### Timings (for 10 samples)
```javascript
{'qpu_sampling_time': 814,
 'qpu_anneal_time_per_sample': 20,
 'qpu_readout_time_per_sample': 40,
 'qpu_access_time': 17892,
 'qpu_access_overhead_time': 12402,
 'qpu_programming_time': 17079,
 'qpu_delay_time_per_sample': 21,
 'total_post_processing_time': 286,
 'post_processing_overhead_time': 286}
```


### Problem #2

$$
Q_{QUBO} = \begin{bmatrix}
27 & -8 & 2 & 11\\
& 5 & 11 & -3\\
& & 27 & -8\\
& & & 5
\end{bmatrix}
$$

#### Solution
```bash
   0  1  2  3 energy num_oc. chain_.
0  0  0  0  0    0.0       7     0.0
1  0  0  0  1    5.0       2     0.0
2  0  1  0  0    5.0       1     0.0
['BINARY', 3 rows, 10 samples, 4 variables]
```
#### Timings (for 10 samples)
```javascript
{'qpu_sampling_time': 784,
'qpu_anneal_time_per_sample': 20,
'qpu_readout_time_per_sample': 37,
'qpu_access_time': 17863,
'qpu_access_overhead_time': 17735,
'qpu_programming_time': 17079,
'qpu_delay_time_per_sample': 21,
'total_post_processing_time': 330,
'post_processing_overhead_time': 330}
```