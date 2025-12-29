# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a knowledge portfolio repository containing personal notes and reference materials on mathematics and computer science topics. The repository is structured as a hierarchical collection of markdown documents covering various academic subjects.

## Repository Structure

```
knowledge-portfolio/
├── computer_science/
│   └── machine_learning/
│       ├── discriminant_analysis_and_naive_bayes.md
│       ├── latent_variable_models.md
│       └── linear_regression.md
├── math/
│   ├── linear_algebra/
│   │   └── system_of_linear_eq.md
│   └── probability/
│       └── transformations.md
└── README.md
```

## Content Format and Conventions

All notes are written in markdown format and follow these conventions:

1. **Mathematical Notation**: Documents extensively use LaTeX math notation within markdown
   - Inline math: `$expression$`
   - Display math: `$$expression$$` or `$$\begin{align*}...\end{align*}$$`

2. **Document Structure**: Each document typically follows:
   - Title header (using `=` underline style or `#`)
   - Section headers using `#`, `##`, `###`
   - Bullet points for concepts and explanations
   - Mathematical derivations with proper equation formatting

3. **Topic Organization**:
   - Topics are organized hierarchically by domain (computer_science, math)
   - Subdirectories group related topics (e.g., machine_learning, linear_algebra, probability)
   - File names use snake_case and are descriptive of their content

## Working with This Repository

When adding or modifying content:

1. **Maintain the hierarchy**: Place new documents in the appropriate subject directory
2. **Follow naming conventions**: Use snake_case for filenames, descriptive names
3. **Preserve LaTeX formatting**: Ensure mathematical equations render correctly
4. **Keep consistent structure**: Follow the existing pattern of headers, bullets, and equations
5. **Check mathematical accuracy**: Verify equations and derivations when making changes

## Git Workflow

- Main branch: `main`
- The repository maintains a clean commit history with descriptive commit messages
- Recent commits show files being organized into the proper subject hierarchy