## JMeter Test Plan for Generating Random CPF and CNPJ

This JMeter test plan is designed to generate random CPF (Cadastro de Pessoas Físicas - Brazilian individual taxpayer registry identification) and CNPJ (Cadastro Nacional da Pessoa Jurídica - Brazilian legal entity identification) using BeanShell scripts. The generated CPF and CNPJ are then used in an HTTP request to post data to [jsonplaceholder.typicode.com/posts](https://jsonplaceholder.typicode.com/posts).

### Test Plan Overview

The test plan consists of the following components:

1. **Test Plan Configuration:**
   - Configuration of the test plan with user-defined variables such as email and classpath for SQL driver.

2. **Thread Group:**
   - Thread group configuration with 10 threads and a loop of 1 iteration, simulating concurrent users.

3. **BeanShell Sampler - CNPJ Generator:**
   - BeanShell script generating a random CNPJ using a mathematical algorithm.

4. **Regex Extractor - Extract CNPJ:**
   - Regular Expression Extractor to capture the generated CNPJ for later use.

5. **BeanShell Sampler - CPF Generator:**
   - BeanShell script generating a random CPF using a mathematical algorithm.

6. **Regex Extractor - Extract CPF:**
   - Regular Expression Extractor to capture the generated CPF for later use.

7. **HTTP Request - Post Data:**
   - HTTP sampler sending a POST request to [jsonplaceholder.typicode.com/posts](https://jsonplaceholder.typicode.com/posts) with the generated CPF, CNPJ, and email as parameters in the request body.

8. **HTTP Header Manager:**
   - Configuration of the HTTP header with "Content-Type: application/json;charset=UTF-8."

9. **Result Collector - View Results Tree:**
   - Result collector for visualizing and analyzing the test results.

### How to Run

1. Ensure you have Apache JMeter installed on your system.
2. Open JMeter and load this test plan.
3. Run the test plan.

### Customization

- Adjust the number of threads and loop iterations in the Thread Group for different concurrency scenarios.
- Modify the BeanShell scripts to customize the logic for generating CPF and CNPJ if needed.
- Update the HTTP request to target a different endpoint or modify the request parameters as necessary.

### Important Note

This test plan is designed for educational and testing purposes only. Generating random CPF and CNPJ for real-world applications may have legal and ethical implications. Use responsibly and in compliance with relevant regulations.
