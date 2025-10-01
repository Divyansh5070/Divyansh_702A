# Divyansh_702A

O1 LAB MST JAVA 
import java.util.*;

class Employee {
    int empID;
    String name;
    String department;
    double salary;

    Employee(int id, String name, String dept, double salary) {
        this.empID = id;
        this.name = name;
        this.department = dept;
        this.salary = salary;
    }

    @Override
    public String toString() {
        return "ID: " + empID +
                " | Name: " + name +
                " | Department: " + department +
                " | Salary: " + salary;
    }
}

public class Main {
    private LinkedList<Employee> employees = new LinkedList<>();

    public void addEmployee(int id, String name, String dept, double salary) {
        employees.add(new Employee(id, name, dept, salary));
        System.out.println("Employee added successfully!");
    }

    public void displayEmployees() {
        if (employees.isEmpty()) {
            System.out.println("No employees to display.");
            return;
        }
        System.out.println("\n--- Employee List ---");
        for (Employee emp : employees) {
            System.out.println(emp);
        }
    }

    public void removeEmployee(int id) {
        boolean removed = false;
        Iterator<Employee> it = employees.iterator();
        while (it.hasNext()) {
            Employee emp = it.next();
            if (emp.empID == id) {
                it.remove();
                System.out.println("Employee with ID " + id + " removed successfully!");
                removed = true;
                break;
            }
        }
        if (!removed) {
            System.out.println("Employee with ID " + id + " not found!");
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Main ems = new Main();

        int choice;
        do {
            System.out.println("\nEmployee Management System");
            System.out.println("1. Add New Employee");
            System.out.println("2. Display All Employees");
            System.out.println("3. Remove Employee");
            System.out.println("4. Exit");
            System.out.print("Enter your choice: ");
            choice = sc.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter Employee ID: ");
                    int id = sc.nextInt();
                    sc.nextLine();
                    System.out.print("Enter Name: ");
                    String name = sc.nextLine();
                    System.out.print("Enter Department: ");
                    String dept = sc.nextLine();
                    System.out.print("Enter Salary: ");
                    double salary = sc.nextDouble();
                    ems.addEmployee(id, name, dept, salary);
                    break;
                case 2:
                    ems.displayEmployees();
                    break;
                case 3:
                    System.out.print("Enter Employee ID to remove: ");
                    int removeId = sc.nextInt();
                    ems.removeEmployee(removeId);
                    break;
                case 4:
                    System.out.println("Exiting...");
                    break;
                default:
                    System.out.println("Invalid choice! Try again.");
            }
        } while (choice != 4);

        sc.close();
    }
}



Q2 LAB MST JAVA 
