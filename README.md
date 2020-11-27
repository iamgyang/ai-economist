# Foundation: An Economic Simulation Framework

This repo contains an implementation of Foundation, a framework for flexible, modular, and composable environments that **model socio-economic behaviors and dynamics in a society with both agents and governments**.

Foundation provides a [Gym](https://gym.openai.com/)-style API:

- `reset`: resets the environment's state and returns the observation.
- `step`: advances the environment by one timestep, and returns the tuple *(observation, reward, done, info)*.

This simulation can be used in conjunction with reinforcement learning to learn optimal economic policies, as detailed in:

**[The AI Economist: Improving Equality and Productivity with AI-Driven Tax Policies](https://arxiv.org/abs/2004.13332)**,
*Stephan Zheng, Alexander Trott, Sunil Srinivasa, Nikhil Naik, Melvin Gruesbeck, David C. Parkes, Richard Socher.*

If you use this code in your research, please cite us using this BibTeX entry:

```
@misc{2004.13332,
  Author = {Stephan Zheng, Alexander Trott, Sunil Srinivasa, Nikhil Naik, Melvin Gruesbeck, David C. Parkes, Richard Socher},
  Title = {The AI Economist: Improving Equality and Productivity with AI-Driven Tax Policies},
  Year = {2020},
  Eprint = {arXiv:2004.13332},
}
```

For more information and context, check out:

- [The AI Economist website](https://www.einstein.ai/the-ai-economist)
- [Blog: The AI Economist: Improving Equality and Productivity with AI-Driven Tax Policies](https://blog.einstein.ai/the-ai-economist/)
- [Blog: The AI Economist moonshot](https://blog.einstein.ai/the-ai-economist-moonshot/)

## Simulation Card: Ethics Review and Intended Use

Please see our [Simulation Card](https://www.github.com/salesforce/ai-economist/blob/master/Simulation_Card_Foundation_Economic_Simulation_Framework.pdf) for a review of the intended use and ethical review of our framework.

## Join us on Slack

If you're interested in extending this framework, discussing machine learning for economics, and collaborating on research project:

- join our Slack channel [aieconomist.slack.com](https://aieconomist.slack.com) using this [invite link](https://join.slack.com/t/aieconomist/shared_invite/zt-g71ajic7-XaMygwNIup~CCzaR1T0wgA), or
- email us @ ai.economist@salesforce.com.

## Installation Instructions

To get started, you'll need to have Python 3.6+ installed.

### Using pip

Simply use the Python package manager:

```python
pip install ai-economist
```

### Installing from Source

1. Clone this repository to your local machine:

    ```
    git clone www.github.com/salesforce/ai-economist
    ```

2. Create a new conda environment (named "ai-economist" below - replace with anything else) and activate it

    ```pyfunctiontypecomment
    conda create --name ai-economist python=3.6
    conda activate ai-economist
    ```

3. Either

    a) Edit the PYTHONPATH to include the ai-economist directory
    ```
    export PYTHONPATH=<local path to ai-economist>:$PYTHONPATH
    ```

    OR

    b) Install as an editable Python package
    ```pyfunctiontypecomment
    cd ai-economist
    pip install -e .
    ```

Useful tip: for quick access, add the following to your ~/.bashrc or ~/.bash_profile:

```pyfunctiontypecomment
alias aiecon="conda activate ai-economist; cd <local path to ai-economist>"
```

You can then simply run `aiecon` once to activate the conda environment.

### Testing your Install

To test your installation, try running:

```
conda activate ai-economist
python -c "import ai_economist"
```

## Getting Started

### Tutorials

To familiarize yourself with Foundation, check out the tutorials in the `tutorials` folder. You can run these notebooks interactively in your browser on Google Colab.

- [tutorials/economic_simulation_basic.ipynb](https://www.github.com/salesforce/ai-economist/blob/master/tutorials/economic_simulation_basic.ipynb) ([Try this on Colab](http://colab.research.google.com/github/salesforce/ai-economist/blob/master/tutorials/economic_simulation_basic.ipynb)!): Shows how to interact with and visualize the simulation.
- [tutorials/economic_simulation_advanced.ipynb](https://www.github.com/salesforce/ai-economist/blob/master/tutorials/economic_simulation_advanced.ipynb) ([Try this on Colab](http://colab.research.google.com/github/salesforce/ai-economist/blob/master/tutorials/economic_simulation_advanced.ipynb)!): Explains how Foundation is built up using composable and flexible building blocks.

To run these notebooks *locally*, you need [Jupyter](https://jupyter.org). See [https://jupyter.readthedocs.io/en/latest/install.html](https://jupyter.readthedocs.io/en/latest/install.html) for installation instructions and [(https://jupyter-notebook.readthedocs.io/en/stable/](https://jupyter-notebook.readthedocs.io/en/stable/) for examples of how to work with Jupyter.

## Structure of the Code

The simulation is located in the `ai_economist/foundation` folder.

The code repository is organized into the following components:

| Component | Description |
| --- | --- |
| [base](https://www.github.com/salesforce/ai-economist/blob/master/ai_economist/foundation/base) | Contains base classes to can be extended to define Agents, Components and Scenarios. |
| [agents](https://www.github.com/salesforce/ai-economist/blob/master/ai_economist/foundation/agents) | Agents represent economic actors in the environment. Currently, we have mobile Agents (representing workers) and a social planner (representing a government). |
| [entities](https://www.github.com/salesforce/ai-economist/blob/master/ai_economist/foundation/entities) | Endogenous and exogenous components of the environment. Endogenous entities include labor, while exogenous entity includes landmarks (such as Water and Grass) and collectible Resources (such as Wood and Stone). |
| [components](https://www.github.com/salesforce/ai-economist/blob/master/ai_economist/foundation/components) | Components are used to add some particular dynamics to an environment. They also add action spaces that define how Agents can interact with the environment via the Component. |
| [scenarios](https://www.github.com/salesforce/ai-economist/blob/master/ai_economist/foundation/scenarios) | Scenarios compose Components to define the dynamics of the world. It also computes rewards and exposes state for visualization. |

## Releases and Contributing

- Please let us know if you encounter any bugs by filing a Github issue.
- We appreciate all your contributions. If you plan to contribute new Components, Scenarios Entities, or anything else, please see our [contribution guidelines](https://www.github.com/salesforce/ai-economist/blob/master/CONTRIBUTING.md).

## Changelog

Current version: v1.1.1

For the complete release history, see [CHANGELOG.md](https://www.github.com/salesforce/ai-economist/blob/master/CHANGELOG.md).

## License

Foundation and the AI Economist are released under the [BSD-3 License](LICENSE.txt).
