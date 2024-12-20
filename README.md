Overview
This repository contains a Python implementation of a Tsetlin Machine model applied to a hex game dataset. The code utilizes various libraries for data manipulation, machine learning, and graph representation. The model's goal is to classify game states based on board configurations.

Table of Contents
Requirements
Installation
Usage
Code Structure
Functions
Results
License
Requirements
Ensure you have the following libraries installed:

numpy
pandas
scikit-learn
matplotlib
tqdm
GraphTsetlinMachine (install via pip or from source)
You can install the required libraries using pip:

Copy
pip install numpy pandas scikit-learn matplotlib tqdm
Installation
Clone the repository to your local machine:

Copy
git clone <repository-url>
cd <repository-directory>
Usage
To run the model, execute the main script. You can specify various parameters via command-line arguments:

Copy
python main.py --epochs <number_of_epochs> --number-of-clauses <number_of_clauses> ...
Command-line Arguments
--epochs: Number of training epochs (default: 20)
--number-of-clauses: Number of clauses in the Tsetlin Machine (default: 20000)
--T: Number of Tsetlin automata (default: 12000)
--s: The learning rate (default: 1)
--depth: The depth of the Tsetlin Machine (default: 2)
--hypervector-size: Size of the hypervector (default: 64)
--hypervector-bits: Number of bits in the hypervector (default: 2)
--message-size: Size of the message (default: 64)
--message-bits: Number of bits in the message (default: 2)
--double-hashing: Enable double hashing (default: False)
--max-included-literals: Maximum number of included literals (default: 32)
Code Structure
main.py: The main script that runs the Tsetlin Machine model.
data_loader.py: Contains functions to load and preprocess the dataset.
graph_creator.py: Functions to create graphs from the board states.
tsetlin_machine.py: Implementation of the MultiClass Tsetlin Machine.
Functions
load_data(input_file, sample_fraction=1, max_rows=None)
Loads the hex game data from a CSV file and returns features and labels.

create_graphs(X_data, is_training=True)
Creates training graphs from the input data.

add_edges(graphs, X_data)
Adds edges between nodes in the graph based on valid neighbors.

get_valid_neighbors(q, r, dim)
Returns valid neighboring coordinates for a given position on the board.

calculate_cluster_size(q, r, symbol, graph_id, visited)
Calculates the cluster size for a given symbol starting from a specific position.
