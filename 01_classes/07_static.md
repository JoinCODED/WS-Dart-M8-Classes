Static class variables are variables that belongs to the class itself, and can be used and assigned without creating an instance of the class, for example:

```dart
class Employee {
    Employee(this.employeeName,this.employeeSalary);
   static String employeeDepartment = "Unknown";
   String employeeName;
   int employeeSalary;

   showEmpInfo(){
     print("Employee's Name Is : ${employeeName}");
     print("Employee's Salary Is : ${employeeSalary}");
     print("Employee's Dept. Is : ${employeeDepartment}");
   }
}

void main() {
  Employee.employeeDepartment = "Design";
  Employee ahmad = Employee("Ahmad",500);
  Employee salem = Employee("Salem",700);

  ahmad.showEmpInfo();
  salem.showEmpInfo();

  Employee.employeeDepartment = "Development";
  Employee khaled = Employee("Khaled",5000);
  Employee aziz = Employee("Aziz",7000);

  khaled.showEmpInfo();
  aziz.showEmpInfo();

}
```

Output:

```
Employee's Name Is : Ahmad
Employee's Salary Is : 500
Employee's Dept. Is : Design
Employee's Name Is : Salem
Employee's Salary Is : 700
Employee's Dept. Is : Design
Employee's Name Is : Khaled
Employee's Salary Is : 5000
Employee's Dept. Is : Development
Employee's Name Is : Aziz
Employee's Salary Is : 7000
Employee's Dept. Is : Development
```
