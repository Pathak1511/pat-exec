**pat-exec Documentation**

---

**Introduction**

`pat-exec` is a versatile package designed to execute code snippets written in various programming languages. It simplifies the process of testing and running code by providing a straightforward interface to pass input, language specifications, code, and a callback function to handle the response or errors.

---

**Installation**

To use `pat-exec` in your project, you can install it via npm:

```bash
npm install pat-exec
```

---

**Usage**

The primary function provided by `pat-exec` is used to execute code snippets. Below is the syntax for utilizing the package:

```javascript
const execute = require("pat-exec");

execute(input, language, code, callback);
```

Parameters:

- `input`: A string representing the input data required for the code execution.
- `language`: A string specifying the programming language of the code snippet.
- `code`: A string containing the code snippet to be executed.
- `callback`: A function to handle the response or errors. It follows the standard Node.js callback pattern `(error, data) => {}`.

---

**Example**

Below is an example demonstrating how to use `pat-exec` to execute a C++ code snippet:

```javascript
const execute = require("pat-exec");

const data = {
  language: "c++",
  code: `#include <iostream>
  using namespace std;
  int main() {
     int n;
     cin>>n;
     int arr[n];
     for(int i=0;i<n;i++) cin>>arr[i];
     for(int i=0;i<n;i++) cout<<arr[i]<<endl;
     cout<<"you entered : "<<n<<endl;
     return 0;
  }`,
  input: "5 6 7 8 9 10",
};

execute(data.input, data.language, data.code, (error, data) => {
  if (error) {
    console.error("Error:", error);
  } else {
    console.log("Data:", data);
  }
});
```

Sample Response :

```
Data: {"output":"6\n7\n8\n9\n10\nyou entered : 5\n"}

```

The data is send as string. Make sure to remove new line '\n' and preprocess data

In this example, we specify the language as `"c++"`, provide the C++ code snippet, input data `"5 6 7 8 9 10"`, and define a callback function to handle the response or errors.

---

**Supported Languages**

Currently, `pat-exec` supports the execution of code snippets in various programming languages, including but not limited to:

- C
- C++
- Python
- JavaScript
- Java
- Ruby
- go
- rust
- php
- typescript

Make sure to pass language as:

- c++
- java
- python
- c
- javascript
- ruby
- go
- rust
- php
- typescript

Additional language support may be added in future updates.

---

**Contributing and Testing**

We welcome contributors to test `pat-exec` and provide feedback on its functionality with different programming languages. To facilitate this, we've developed a client-side application using Next.js where you can interactively test the `pat-exec` package.

**Accessing the Code Editor**

You can access the code editor application at [CodeFlow Studio](https://codeflow-studio.vercel.app/). This application allows you to:

- Choose a programming language from the provided list.
- Enter custom code snippets.
- Provide input data.
- Execute the code using `pat-exec`.
- Handle the response or errors.

**How to Contribute**

1. **Testing Supported Languages**:

   - Visit [CodeFlow Studio](https://codeflow-studio.vercel.app/).
   - Select different programming languages supported by `pat-exec`.
   - Write code snippets and test with varying inputs.
   - Verify the responses and functionality.

2. **Reporting Issues**:
   - If you encounter any errors or unexpected behavior while using `pat-exec` with the CodeFlow Studio app, please [report the issues](mailto:hritikpathak888@gmail.com).
   - Provide detailed descriptions of the problem along with the programming language, code snippet, input data, and observed output/error.

### Contributing to `pat-exec` Open Source

After testing and familiarizing yourself with `pat-exec` through the CodeFlow Studio app, we encourage you to contribute to the development of `pat-exec` on GitHub.

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/Pathak1511/pat-exec.git
   ```

2. **Set Up Development Environment**:

   ```bash
   cd pat-exec
   npm install
   ```

3. **Make Changes**:

   - Implement fixes or new features.
   - Improve documentation.

4. **Submit Pull Requests**:
   - Push your changes to a new branch:
     ```bash
     git checkout -b feature-name
     git add .
     git commit -m "Description of changes"
     git push origin feature-name
     ```
   - Open a pull request on GitHub.

### Contact

For further inquiries, issues, or collaboration opportunities, please reach out to the package maintainer at [hritikpathak888@gmail.com](mailto:hritikpathak888@gmail.com).

We appreciate your interest in contributing to `pat-exec` and hope you find it a valuable tool for your coding endeavors!

---
