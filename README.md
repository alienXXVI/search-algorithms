# Encrypted Chat TCP/UDP

## Description
This project implements three distinct graph search algorithms to solve pathfinding problems, specifically modeled after the "Labyrinth of Crete" challenge. It features an interactive command-line interface that allows users to load custom graph files, visualize graph summaries, and compare the efficiency and path quality of different search strategies.

## Technologies
-   **C++11** or superior
-   **Standard Template Library (STL)**
-   **Linux, MacOS, or Windows (MinGW/MSYS2)**

## Prerequisites
To compile and execute this project, you must have one of the following installed:
-   **GCC (g++)**
-   **Clang**

## Features
-   **Algorithm Variety**: Implements Depth-First Search (DFS) for basic exploration, A* for optimal heuristic-based pathfinding, and a specialized Dijkstra for constrained movement.
-   **Heuristic Support**: Utilizes $h(n)$ values to guide the A* search toward the goal node efficiently.
-   **Performance Metrics**: Tracks and displays "Expanded Nodes" to measure the computational efficiency of each search.
-   **Custom Parser**: Reads graph definitions from text files, supporting both directed and undirected edges with associated costs.
-   **Bonus Dijkstra**: A unique "Limited Wire" implementation of Dijkstra that discards paths exceeding a user-defined total distance.

## How to Run

### 1. Compiling

Navigate to the `src/` folder and run the following command to compile all files:

    cd src
    g++ -std=c++11 *.cpp -o busca

### 2. Execution

To start the program, execute the following command in your terminal:

    ./busca

### 3. Step-by-Step Instructions

1.  **Load a Graph**: Select **Option 1** and enter the input filename (e.g., `exemplo1.txt`). The file must be located inside the `input/` folder.
2.  **View Summary**: The program will display the nodes, their heuristics, and their neighbors.
3.  **Run Algorithms**:
    -   **Option 2**: Executes Depth-First Search (DFS).
    -   **Option 3**: Executes the A* algorithm.
    -   **Option 4**: Executes the Uniform Cost (Dijkstra) algorithm with a wire limit (the program will prompt for the limit value).
4.  **Exit**: Select **Option 0** to terminate the program.

## Input File Format
Graphs must be defined in a text file using the following format:

    ponto_inicial(a0).       % Starting point
    ponto_final(f0).         % Target point
    orientado(s).            % 's' for directed, 'n' for undirected
    pode_ir(a0,b0,95).       % Edge between a0 and b0 with cost 95
    h(a0,f0,58).             % Heuristic distance from a0 to f0 is 58

-   `orientado`: Defines if the graph is directed.
-   `ponto_inicial` / `ponto_final`: Define the start and goal nodes.
-   `pode_ir`: Defines connections and their costs.
-   `h`: Heuristic value (used for A*).

## Project Structure

-   **`src/`**: Source code files including `main.cpp`, `graph`, `dfs`, `astar`, `dijkstra`, and `parser`.
-   **`input/`**: Directory containing graph input files (e.g., `exemplo_pequeno.txt`, `exemplo_medio.txt`).
-   **`README.md`**: Project documentation.

## What I Learned

-   **Algorithm Design**: Practical application of $f(n) = g(n) + h(n)$ to optimize search space exploration in A*.
-   **Memory Management**: Efficiently using `unordered_map` and `unordered_set` for $O(1)$ lookups of visited nodes and costs.
-   **Data Parsing**: Implementing a robust parser to handle file comments (`%`) and specific formatting rules.
-   **Problem Constraints**: Integrating physical limitations (the "wire" limit) into standard shortest-path algorithms.


## Future Improvements

-   **Visual Representation**: Implement a graphical visualization of the maze and the expansion of the search frontier.
-   **Enhanced Heuristics**: Add support for different heuristic calculations, such as Manhattan or Euclidean distance.
-   **Bidirectional Search**: Implement bidirectional A* to further reduce the number of expanded nodes for large graphs.


