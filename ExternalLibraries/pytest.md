
---

# **🔥 Pytest:Python Testing Framework! 🧪**
✅ **What is Pytest?**  
Pytest is a **powerful, easy-to-use testing framework** in Python that helps you write reliable and scalable tests with minimal boilerplate code.  

🔹 Ideal for **unit testing, integration testing, and functional testing**  
🔹 Uses **simple `assert` statements** (no need for `unittest` complexity)  
🔹 Has **fixtures for setup & teardown** to avoid redundant code  
🔹 Supports **parameterized testing** for multiple test scenarios  
🔹 Provides **detailed test reports**  

Let's **dive deep** into Pytest with **hands-on examples** in Jupyter Notebook! 🚀  

---

## **📌 1. Installing & Setting Up Pytest in Jupyter Notebook**
Since Jupyter Notebook doesn’t support direct execution of `pytest`, we use **pytest-ipynb**, a plugin that enables running Pytest inside notebooks.  

**🔹 Install Pytest & Required Plugins:**  
```python
!pip install pytest pytest-ipynb
```

**🔹 Check Pytest Version:**  
```python
!pytest --version
```

📢 **Now we are ready to write and run tests inside Jupyter Notebook!** ✅  

---

## **📌 2. Writing Your First Pytest Function 🎯**
Let’s start with a **simple function** and write a **test for it!**  

**🔹 Example: Adding Two Numbers**
```python
def add(x, y):
    return x + y
```

### **📝 Writing a Test Case for `add()`**
In Pytest, **test functions must:**  
✅ Start with `test_`  
✅ Use **assert statements** to verify the expected output  

```python
def test_add():
    assert add(2, 3) == 5  # ✅ Test should pass
    assert add(-1, 1) == 0  # ✅ Test should pass
    assert add(0, 0) == 0  # ✅ Test should pass
```

---

## **📌 3. Running Pytest Inside Jupyter Notebook 🚀**
Since Jupyter Notebook doesn’t support direct `pytest` execution, use **the `%%pytest` magic command** inside a cell:  

```python
%%pytest
def test_example():
    assert 1 + 1 == 2  # ✅ Should pass
```

🔹 If running tests inside a Python script (`.py` file), execute Pytest with:  
```bash
pytest test_file.py
```

---

## **📌 4. Testing Multiple Inputs with `pytest.mark.parametrize` 🎭**  
Instead of writing separate test cases for different inputs, we can **parameterize** them!  

**🔹 Example: Testing with Multiple Inputs**
```python
import pytest

@pytest.mark.parametrize("a, b, expected", [
    (1, 2, 3),
    (0, 0, 0),
    (-1, -1, -2),
    (100, 200, 300)
])
def test_addition(a, b, expected):
    assert add(a, b) == expected
```
🚀 **Why use `parametrize`?**  
- Reduces redundant test cases  
- Makes test functions **cleaner and scalable**  

---

## **📌 5. Using Fixtures for Setup & Teardown 🔧**  
Pytest **fixtures** allow **reusable setup and teardown** logic before and after tests run.

**🔹 Example: Using a Fixture to Provide Sample Data**
```python
import pytest

@pytest.fixture
def sample_data():
    return {"name": "Alice", "age": 30}

def test_sample_data(sample_data):
    assert sample_data["name"] == "Alice"
    assert sample_data["age"] == 30
```

🔥 **Why use fixtures?**  
- **Avoids duplicate setup code**  
- **Keeps test cases clean and modular**  

---

## **📌 6. Handling Expected Errors with `pytest.raises` ⚠️**
Testing should **verify that errors occur** when expected.  

### **🔹 Example: Testing an Exception**
```python
def divide(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero!")
    return a / b

def test_divide():
    with pytest.raises(ValueError, match="Cannot divide by zero!"):
        divide(10, 0)  # ✅ Should raise an error
```

🚀 **Why use `raises`?**  
- Ensures your code **correctly raises exceptions**  
- Helps test **error handling logic**  

---

## **📌 7. Running Specific Tests 🏃‍♂️**  
Pytest provides options to **run only specific test cases** instead of executing everything.  

### **Run All Tests in the Directory**
```bash
pytest
```

### **Run a Specific Test File**
```bash
pytest test_sample.py
```

### **Run a Specific Test Function**
```bash
pytest -k "test_addition"
```

---

## **📌 8. Generating Test Reports 📄**  

### **Show Detailed Output**
```bash
pytest -v
```

### **Generate an HTML Report**
```bash
pytest --html=report.html
```
💡 **This creates a user-friendly test report in `report.html`!**  

---

## **📌 9. Skipping & Marking Tests ⏩**  
Sometimes, we may need to **skip** or **conditionally run** tests.

### **🔹 Skip a Test**
```python
@pytest.mark.skip(reason="Skipping this test for now")
def test_skip():
    assert 1 == 2  # ❌ Won’t be executed
```

### **🔹 Run a Test Only on a Specific Condition**
```python
import sys

@pytest.mark.skipif(sys.version_info < (3, 8), reason="Requires Python 3.8+")
def test_python_version():
    assert 1 + 1 == 2
```

---

## **📌 10. Organizing Tests with Classes 🎭**  
For **better structure**, we can group test functions into **classes**.  

```python
class TestMathOperations:
    def test_add(self):
        assert add(4, 6) == 10
    
    def test_multiply(self):
        assert 3 * 3 == 9
```

🚀 **Why use classes?**  
- Groups related test cases together  
- Useful for **testing object-oriented code**  

---

# **🚀 Summary & Next Steps**
✅ **Pytest simplifies testing with easy-to-read assertions**  
✅ **Supports fixtures, parameterized tests, and exception handling**  
✅ **Works inside Jupyter Notebook with `pytest-ipynb`**  
✅ **Allows skipping, running selective tests, and generating reports**  

---
