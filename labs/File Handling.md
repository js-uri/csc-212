# File I/O

In C++, you can read and write to files using the <fstream> library, which provides classes like ifstream and ofstream for file input and output operations, respectively. Here's an example of how to read from and write to a file in C++:

``` cpp
#include <iostream>
#include <fstream>

int main() {
    // Open a file for writing
    std::ofstream outputFile("example.txt");

    if (outputFile.is_open()) {
        // Write to the file
        outputFile << "Hello, World!\n";
        outputFile << "This is a sample file.\n";

        // Close the file
        outputFile.close();
        std::cout << "File write operation completed." << std::endl;
    } else {
        std::cout << "Unable to open the file." << std::endl;
        return 1;
    }

    // Open the file for reading
    std::ifstream inputFile("example.txt");

    if (inputFile.is_open()) {
        std::string line;

        // Read and print each line from the file
        while (std::getline(inputFile, line)) {
            std::cout << line << std::endl;
        }

        // Close the file
        inputFile.close();
        std::cout << "File read operation completed." << std::endl;
    } else {
        std::cout << "Unable to open the file." << std::endl;
        return 1;
    }

    return 0;
}
```

In this example, we first open a file named "example.txt" for writing using an ofstream object. We check if the file was opened successfully using the is_open() function. Then, we write some lines of text to the file using the << operator.

After writing, we close the file using the close() function and print a message to indicate the completion of the write operation.

Next, we open the same file for reading using an ifstream object. Again, we check if the file was opened successfully. Then, we read the file line by line using the getline() function and print each line to the console.

Finally, we close the file using the close() function and print a message to indicate the completion of the read operation.

Remember to include the <fstream> header at the beginning of your program to use the file stream classes and the <iostream> header for input/output operations.
