
# Memory Leak Visualization Tool

The Memory Leak Visualization Tool is a C++ project designed to monitor, track, and visualize memory allocations and deallocations in real-time. It logs memory usage information, including size, timestamp, and thread ID, and exports this data to a JSON file for analysis.

---

## Directory Structure

```
MemoryLeakVisualizationTool/
├── CppTracker/
│   ├── memory_tracker.h
│   ├── memory_tracker.cpp
│   └── main.cpp
├── memory_data.json
└── README.md
```

---

## Setup Instructions

1. **Clone or Download the Repository**:
   ```bash
   git clone https://github.com/your-repo/MemoryLeakVisualizationTool.git
   cd MemoryLeakVisualizationTool/CppTracker
   ```

2. **Install Required Libraries**:
   - The tool uses the `nlohmann/json.hpp` library for JSON handling.
   - Download the single-header library from [nlohmann/json GitHub Releases](https://github.com/nlohmann/json/releases).
   - Place the `json.hpp` file in the `CppTracker` directory.

3. **Compile the Code**:
   Use the following command to compile the project:
   ```bash
   g++ -o memory_tracker main.cpp memory_tracker.cpp -pthread
   ```

4. **Run the Executable**:
   ```bash
   ./memory_tracker
   ```

5. **Check the Output**:
   The program will generate a `memory_data.json` file containing memory allocation data in real-time.

---

## Required Libraries and Dependencies

1. **C++ Standard Library**:
   - The tool requires C++17 or later for features like `std::chrono` and `std::mutex`.

2. **`nlohmann/json`**:
   - Used for JSON serialization and manipulation.
   - Download the header-only file (`json.hpp`) from [nlohmann/json GitHub Releases](https://github.com/nlohmann/json/releases).

3. **Compiler**:
   - A modern C++ compiler with support for C++17 (e.g., GCC, Clang).

---

## Configuration Details

### `memory_tracker.h`:
- Contains the `MemoryTracker` class definition.
- Core functionalities:
  - `TrackMalloc(size_t size)`: Allocates and logs memory.
  - `TrackFree(void* ptr)`: Frees memory and updates the map.
  - `ExportToJSON()`: Exports tracking data to a JSON file.

### `memory_tracker.cpp`:
- Implements the `MemoryTracker` methods with thread-safe operations.

### `main.cpp`:
- Simulates memory usage and exports JSON data in real-time.

### `memory_data.json`:
- Stores memory allocation data in the following format:
  ```json
  [
      {
          "address": 140727434928832,
          "size": 1024,
          "thread_id": 12345678,
          "timestamp": 1700000000000
      }
  ]
  ```

---

## Example Output

Sample content of `memory_data.json` after running the tool:

```json
[
    {
        "address": 140727434928832,
        "size": 1024,
        "thread_id": 12345678,
        "timestamp": 1700000000000
    },
    {
        "address": 140727434929856,
        "size": 2048,
        "thread_id": 12345678,
        "timestamp": 1700000000500
    }
]
```

---

## Future Improvements

- **Visualization**: Develop a frontend or use Python scripts to visualize memory trends.
- **Enhanced Tracking**: Extend the tool to support custom memory allocators.
- **Performance Metrics**: Add profiling to measure tracking overhead.

---

## License

This project is licensed under the MIT License.
"# Memory-Visualizer" 
