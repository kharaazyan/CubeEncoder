```markdown
# CubeEncoder

CubeEncoder is a C++ library that provides encoding and decoding functionalities using a cube-based cipher. It allows you to perform various transformations such as shifting rows and columns, as well as swapping elements diagonally.

## Features

- **Right Encoding**: Shifts each row to the right.
- **Left Encoding**: Shifts each row to the left.
- **Up Encoding**: Shifts the entire cube upwards.
- **Down Encoding**: Shifts the entire cube downwards.
- **X Encoding**: Swaps elements along the diagonal.

## Project Structure

```
CubeEncoder/
├── include/
│   └── CubeEncoder.hpp
├── src/
│   └── CubeEncoder.cpp
├── main.cpp
└── README.md
```

- **include/CubeEncoder.hpp**: Header file containing the `CubeEncoder` class declaration.
- **src/CubeEncoder.cpp**: Source file containing the implementation of the `CubeEncoder` class.
- **main.cpp**: Example usage of the `CubeEncoder` class.
- **README.md**: Project documentation.

## Requirements

- C++11 or higher
- C++ Compiler (e.g., g++, clang++)

## Building the Project

1. **Clone the Repository**

   ```bash
   git clone https://github.com/kharaazyan/CubeEncoder.git
   cd CubeEncoder
   ```

2. **Create a Build Directory**

   It's a good practice to build your project in a separate directory.

   ```bash
   mkdir build
   cd build
   ```

3. **Compile the Project**

   Assuming you have `g++` installed, you can compile the project using the following command:

   ```bash
   g++ -std=c++11 ../src/CubeEncoder.cpp ../main.cpp -I../include -o CubeEncoder
   ```

   - `-std=c++11`: Specifies the C++ standard.
   - `-I../include`: Includes the header files from the `include` directory.
   - `-o CubeEncoder`: Names the output executable `CubeEncoder`.

4. **Run the Executable**

   ```bash
   ./CubeEncoder
   ```

   **Sample Output:**

   ```
   Encoded: <encoded_string>
   Decoded: Hovhannes Kharazyan
   ```

## Usage

To use the `CubeEncoder` class in your project:

1. **Include the Header**

   ```cpp
   #include "CubeEncoder.hpp"
   ```

2. **Create an Instance**

   ```cpp
   CubeEncoder encoder("Your text here");
   ```

3. **Encode**

   ```cpp
   std::string encoded = encoder.encode(CubeEncoder::Coder::right);
   ```

4. **Decode**

   ```cpp
   std::string decoded = encoder.decode(CubeEncoder::Coder::right);
   ```

## Example

Here's a simple example of how to use the `CubeEncoder` class in your `main.cpp`:

```cpp
#include <iostream>
#include "CubeEncoder.hpp"

int main(){
    CubeEncoder encoder("Hovhannes Kharazyan");
    
    // Encode with 'right' and then 'x'
    std::string encoded = encoder.encode(CubeEncoder::Coder::right);
    encoded = encoder.encode(CubeEncoder::Coder::x);    
    std::cout << "Encoded: " << encoded << std::endl;
    
    // Decode with 'x' and then 'right'
    encoder = encoded;
    encoded = encoder.decode(CubeEncoder::Coder::x);
    encoded = encoder.decode(CubeEncoder::Coder::right);
    std::cout << "Decoded: " << encoded << std::endl;
    
    return 0;
}
```

This will output the encoded and then decoded string, demonstrating the encoding and decoding process.

```
Encoded: <encoded_string>
Decoded: Hovhannes Kharazyan
```

Replace `<encoded_string>` with the actual encoded output.

```
