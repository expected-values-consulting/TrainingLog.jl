# TrainingLog

[![Stable](https://img.shields.io/badge/docs-stable-blue.svg)](https://fieldofnodes.github.io/TrainingLog.jl/stable/)
[![Dev](https://img.shields.io/badge/docs-dev-blue.svg)](https://fieldofnodes.github.io/TrainingLog.jl/dev/)
[![Build Status](https://github.com/fieldofnodes/TrainingLog.jl/actions/workflows/CI.yml/badge.svg?branch=main)](https://github.com/fieldofnodes/TrainingLog.jl/actions/workflows/CI.yml?query=branch%3Amain)


# TrainingLog

Welcome to the `TrainingLog` module! This Julia package is designed to facilitate the creation and management of detailed training logs in LaTeX format. It provides tools for generating structured tables that track training progress, including competencies achieved, comments, and trainer signatures.

## Features

- **Customizable Table Generation**: Create detailed training tables with columns for week, competency, achievements, comments, and trainer information.
- **Export to File**: Write the generated LaTeX tables to files for easy integration into your documents.
- **Flexible Layout**: Includes functions for customizing table headers, rows, and footers to fit specific training log requirements.

## Installation

To use `TrainingLog`, ensure that you have Julia installed on your system. You can add this module to your Julia environment by including it in your project or environment:

```julia
] add https://github.com/your-repo/TrainingLog
```

## Usage

Begin by importing the module into your Julia environment:

```julia
using TrainingLog
```

### Generating a Training Table

To generate a LaTeX-formatted training table from a `TrainingTableData` object, use the `generate_table` function:

```julia
training_table = generate_table(ttd::TrainingTableData)
```

This function creates a LaTeX table that includes:

- **Header**: A formatted header using `generate_table_header` that sets up the structure of the table.
- **Rows**: Each row corresponds to a week, content type, and content title, with placeholders for competencies achieved, comments, and trainer details.
- **Footer**: A formatted footer using `generate_table_footer` to close the table.

### Writing the Table to a File

Once the table is generated, you can write it to a file using the `write_table_to_file` function:

```julia
write_table_to_file("training_log.tex", ttd::TrainingTableData)
```

This will create a `.tex` file with the generated table content, ready to be included in a LaTeX document.

### Example Usage

```julia
# Assuming you have already generated `TrainingTableData` from the TrainingContent module
using TrainingContent

# Create some sample content titles
titles = ["Introduction", "Module 1: Basics", "Module 2: Advanced Topics"]

# Generate the training table data
training_data = generate_TrainingTableData(titles; course_length=10)

# Generate the LaTeX training log table as a string
latex_training_log = generate_table(training_data)

# Write the LaTeX training log table to a file
write_table_to_file("my_training_log.tex", training_data)
```

### Customizing the Table Layout

If you need to customize the appearance of the table further, you can modify the `generate_table_header`, `generate_table_row`, and `generate_table_footer` functions to suit your specific formatting requirements.

### Table Structure

- **Week**: Displays the week number.
- **Training Competency**: Lists the competency being addressed.
- **Competency Achieved**: Provides a place to mark whether the competency was achieved (Yes or No).
- **Comments**: A section for additional notes and observations.
- **Trainer Name & Signature**: A space for the trainer's name and signature.

This structure ensures that all necessary information is captured during the training process, making it easier to track progress and address any issues.

## Contributing

Contributions to `TrainingLog` are welcome! Please submit a pull request with your changes or open an issue if you encounter any problems.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions, suggestions, or feedback, feel free to reach out via [GitHub Issues](https://github.com/your-repo/TrainingLog/issues).

---

This README provides an overview of the functionality within `TrainingLog`. For detailed examples and additional information, please refer to the module's source code and documentation.
