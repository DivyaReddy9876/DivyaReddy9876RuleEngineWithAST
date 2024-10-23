# DivyaReddy9876RuleEngineWithAST
Developed a rule engine to dynamically create, combine, and evaluate conditions using an Abstract Syntax Tree (AST). The system determines user eligibility based on attributes such as age, department, and income. This project includes a simple UI, API endpoints, and backend components. Rules are stored in an SQLite database, with a schema designed to support dynamic rule changes and modifications. Additionally, the system allows for combining multiple rules using logical operators like AND and OR, ensuring efficient and accurate evaluations.

The project follows a 3-tier architecture, comprising the user interface, API layer, and backend. The user interface allows for easy rule creation and management. The API layer processes these rules into AST nodes, while the backend performs the evaluations based on user data. Data storage is handled by SQLite, chosen for its simplicity and ease of integration.

Key features include dynamic rule creation with AST, recursive evaluation of conditions, and the ability to modify existing rules. Error handling ensures that invalid rule strings or data formats are managed appropriately, enhancing the system's robustness. Dependencies for the project include Python 3.x, requests, matplotlib, and sqlite3, which are outlined in a requirements.txt file for easy setup.

To get started, clone the repository from GitHub, install the dependencies, and run the application using Python. Detailed setup instructions and design choices are provided in the README.md file included in the repository. The project is licensed under the MIT License, making it open for further development and contributions.

This comprehensive yet straightforward approach makes the rule engine a versatile tool for evaluating complex conditions efficiently and accurately. By leveraging AST for rule representation, the system achieves flexibility and scalability, accommodating various use cases and user requirements. The integration of SQLite ensures persistent storage and easy data retrieval, supporting seamless rule management and evaluation.


The output results of my Python script is as follows :

TEST CASE 1: Create individual rules from the examples using create_rule and verify their AST representation.

AST for rule 1: (('>', 'age', '30') AND ('==', 'department', "'Sales'"))
AST for rule 2: (('>', 'salary', '50000') OR ('>', 'experience', '5'))
AST for rule 3: (('<', 'age', '25') AND ('==', 'department', "'Marketing'"))

TEST CASE 2: Combine the example rules using combine_rules and ensure the resulting AST reflects the combined logic.

Combined AST with AND: (((('>', 'age', '30') AND ('==', 'department', "'Sales'")) AND (('>', 'salary', '50000') OR ('>', 'experience', '5'))) AND (('<', 'age', '25') AND ('==', 'department', "'Marketing'")))

Combined AST with OR: (((('>', 'age', '30') AND ('==', 'department', "'Sales'")) OR (('>', 'salary', '50000') OR ('>', 'experience', '5'))) OR (('<', 'age', '25') AND ('==', 'department', "'Marketing'")))

TEST CASE3: Implement sample JSON data and test evaluate_rule for different scenarios.

User eligibility (for combined rules with AND): False
User eligibility (for combined rules with OR): True
User eligibility (for new data with AND): False
User eligibility (for new data with OR): True

TEST CASE4: Explore combining additional rules and test the functionality.

Testing invalid rule:
TypeError: Invalid comparison between int and str
Evaluation result for invalid rule: False
