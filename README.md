# ROUND2-HASH-TECH
``
NAME: VIJAY KUMAR V R    
COLLEGE NAME: SAVEETHA ENGINEERING COLLEGE 
DEPARTMENT: B.E(CSE) 
``

# Second  Challenge for Hash Agile Internship/Freshers Drive :

# ROUND 2:
QUESTION:
![ROUND2-HASH QUESTION](https://github.com/user-attachments/assets/d73d41a6-7daf-4c09-8eb4-eac4b466b85c)

PROGRAM:[JAVA]

```
import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

class Employee {
    String id;
    String name;
    String department;
    String gender;

    public Employee(String id, String name, String department, String gender) {
        this.id = id;
        this.name = name;
        this.department = department;
        this.gender = gender;
    }

    @Override
    public String toString() {
        return name + " (" + id + ", " + department + ", " + gender + ")";
    }
}

class CollectionManager {
    private Map<String, List<Employee>> collections = new HashMap<>();

    public void createCollection(String collectionName) {
        collections.put(collectionName, new ArrayList<>());
        System.out.println("Collection created: " + collectionName);
    }

    public int getEmpCount(String collectionName) {
        List<Employee> employees = collections.get(collectionName);
        if (employees != null) {
            return employees.size();
        }
        return 0;
    }

    public void indexData(String collectionName, String indexField) {
        System.out.println("Indexing data in " + collectionName + " by " + indexField);
        
    }

    public void delEmpById(String collectionName, String empId) {
        List<Employee> employees = collections.get(collectionName);
        if (employees != null) {
            employees.removeIf(emp -> emp.id.equals(empId));
            System.out.println("Deleted employee with ID: " + empId);
        }
    }

    public List<Employee> searchByColumn(String collectionName, String columnName, String value) {
        List<Employee> employees = collections.get(collectionName);
        List<Employee> result = new ArrayList<>();

        if (employees != null) {
            for (Employee emp : employees) {
                if (columnName.equals("Department") && emp.department.equals(value)) {
                    result.add(emp);
                } else if (columnName.equals("Gender") && emp.gender.equals(value)) {
                    result.add(emp);
                }
            }
        }
        return result;
    }

    public List<String> getDepFacet(String collectionName) {
        List<Employee> employees = collections.get(collectionName);
        List<String> departments = new ArrayList<>();
        if (employees != null) {
            for (Employee emp : employees) {
                if (!departments.contains(emp.department)) {
                    departments.add(emp.department);
                }
            }
        }
        return departments;
    }


    public void addEmployee(String collectionName, Employee employee) {
        List<Employee> employees = collections.get(collectionName);
        if (employees != null) {
            employees.add(employee);
            System.out.println("Added employee: " + employee);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        CollectionManager manager = new CollectionManager();

        // Replace with your name and phone last four digits
        String v_nameCollection = "vijay_kumar";
        String v_phoneCollection = "vijay_kumar_2504";

        manager.createCollection(v_nameCollection);
        manager.createCollection(v_phoneCollection);

        // Adding some sample employees using the new method
        manager.addEmployee(v_nameCollection, new Employee("E02001", "VIJAY_KUMAR", "CSE", "MALE"));
        manager.addEmployee(v_nameCollection, new Employee("E02002", "MUGILAN", "CSE", "Male"));
        manager.addEmployee(v_nameCollection, new Employee("E02003", "DEVASREEMATHI", "ECE", "Female"));

        System.out.println("Employee Count: " + manager.getEmpCount(v_nameCollection));

        manager.indexData(v_nameCollection, "Department");
        manager.indexData(v_phoneCollection, "Gender");

        manager.delEmpById(v_nameCollection, "E02003");
        System.out.println("Employee Count after deletion: " + manager.getEmpCount(v_nameCollection));

        List<Employee> itEmployees = manager.searchByColumn(v_nameCollection, "Department", "CSE");
        System.out.println("Employees in CSE Department: " + itEmployees.size());

        List<Employee> maleEmployees = manager.searchByColumn(v_nameCollection, "Gender", "Male");
        System.out.println("Male Employees: " + maleEmployees.size());

      
        List<Employee> itPhoneEmployees = manager.searchByColumn(v_phoneCollection, "Department", "IT");
        System.out.println("Employees in IT (Phone Collection): " + itPhoneEmployees.size());

        List<String> departmentFacets = manager.getDepFacet(v_nameCollection);
        System.out.println("Department Facets: " + departmentFacets);
    }
}
```
OUTPUT:

![ROUND2-HASH OUTPUT](https://github.com/user-attachments/assets/cc2724dd-7afd-42f8-93db-e2cab203f0f0)

# HTML CODE:
CODE:
```
<html>
<body>
    <h2>Search Employee by Name</h2>
    <input type="text" id="searchName" placeholder="Enter employee name">
    <button onclick="searchEmployee()">Search</button>
    <p id="result"></p>

    <script>
        function searchEmployee() {
            let name = document.getElementById('searchName').value;
            // AJAX call to the backend API to fetch employee data by name
            fetch('/searchByName?name=' + name)
                .then(response => response.json())
                .then(data => {
                    document.getElementById('result').innerHTML = JSON.stringify(data);
                });
        }
    </script>
</body>
</html>
```
# OUTPUT:
![ROUND2-HASH OUTPUT2](https://github.com/user-attachments/assets/3598ce40-a82e-4388-8527-20123bd6ae55)

RESULT:

Thus, the program was executed successfully and implemented .



