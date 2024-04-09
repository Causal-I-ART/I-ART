# iArt: Imputation-Assisted Randomization Tests

## Authors

Jiawei Zhang*, Siyu Heng*, and Yang Feng (* indicates equal contribution)

## Maintainers

Jiawei Zhang (Email: jz4721@nyu.edu), Siyu Heng (Email: siyuheng@nyu.edu), and Yang Feng (Email: yang.feng@nyu.edu)

## iArt (Imputation-Assisted Randomization Tests) Description

Design-based causal inference, also known as randomization-based or finite-population causal inference, is one of the most widely used causal inference frameworks, largely due to the merit that its statistical validity can be guaranteed by the study design (e.g., randomized experiments) and does not require assuming specific outcome-generating distributions or super-population models. Despite its advantages, design-based causal inference can still suffer from other data-related issues, among which outcome missingness is a prevalent and significant challenge. This work systematically studies the outcome missingness problem in design-based causal inference. First, we propose a general and flexible outcome missingness mechanism that can facilitate finite-population-exact randomization tests for the null effect. Second, under this flexible missingness mechanism, we propose a general framework called ``imputation and re-imputation" for conducting finite-population-exact randomization tests in design-based causal inference with missing outcomes. This framework can incorporate any imputation algorithms (from linear models to advanced machine learning-based imputation algorithms) while ensuring finite-population-exact type-I error rate control. Third, we extend our framework to conduct covariate adjustment in randomization tests and construct finite-population-valid confidence sets with missing outcomes. Our framework is evaluated via extensive simulation studies and applied to a large-scale randomized experiment. Corresponding \textsf{Python} and \textsf{R} packages are also developed.

## Installation

To install [iArt](https://pypi.org/project/python-iArt/), run the following command:

```bash
pip install python-iArt
```

## Usage

Here is a basic example of how to use iArt:

```python
import numpy as np
import iArt

Z = [1, 1, 1, 1, 0, 0, 0, 0]
X = [[5.1, 3.5], [4.9, np.nan], [4.7, 3.2], [4.5, np.nan], [7.2, 2.3], [8.6, 3.1], [6.0, 3.6], [8.4, 3.9]]
Y = [[4.4, 0.5], [4.3, 0.7], [4.1, np.nan], [5.0, 0.4], [1.7, 0.1], [np.nan, 0.2], [1.4, np.nan], [1.7, 0.4]]
result = iArt.test(Z=Z, X=X, Y=Y, L=1000, verbose=True)
print(result)
```
Detailed usage can be found here [ReadDoc](https://iart.readthedocs.io/en/latest/)

## Features

- Conducts finite-population-exact randomization tests.
- Handles missing data in causal inference studies.
- Supports various outcome imputation algorithms.
- Offers covariate adjustment in exact randomization tests.


## Contributing

Your contributions to iArt are highly appreciated! If you're looking to contribute, we encourage you to open issues for any bugs or feature suggestions, or submit pull requests with your proposed changes. 

### Setting Up a Development Environment

To set up a development environment for contributing to iArt, follow these steps:

```bash
python -m venv venv
source venv/bin/activate 
pip install -r requirements.txt
python setup.py install
```
This creates a virtual environment (`venv`) for Python and activates it, allowing you to work on the package without affecting your global Python environment.

## License
This project is licensed under the MIT License

## Citation
If you use iArt in your research, please consider citing it:

```code
@misc{heng2023designbased,
      title={Design-Based Causal Inference with Missing Outcomes: Missingness Mechanisms, Imputation-Assisted Randomization Tests, and Covariate Adjustment}, 
      author={Siyu Heng and Jiawei Zhang and Yang Feng},
      year={2023},
      eprint={2310.18556},
      archivePrefix={arXiv},
      primaryClass={stat.ME}
}
```
