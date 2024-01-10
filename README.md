# DSA
Bài tập lớp cấu trúc dữ liệu và giải thuật

package DSA-test-2;

//Cho một danh sách sinh viên


//Index	Name	    Age	Class
//0	Nguyễn Văn A	10	5D4
//1	Nguyễn Văn B	9	4C3
//2	Nguyễn Văn D	8	3B2
//3	Nguyễn Văn D	7	2A1


//1.	Tạo mảng danh sách sinh viên
//2.	Thêm sinh viên vào mảng theo chỉ mục như ở trên
//3.	In toàn bộ danh sách sinh viên ra màn hình
//4.	Tìm kiếm sinh viên có tên là Nguyễn Văn A và in thông tin sinh viên đó ra màn hình
//5.	Tìm kiếm sinh viên nhiều tuổi nhất và in ra màn hình
//6.	Đổi chỗ sinh viên Index 0 với sinh viên index 3. In lại mảng ra màn hình

public class DSA_part2array {
    // Student class definition
    static class Student {
        String name;
        int age;
        String className;

        public Student(String name, int age, String className) {
            this.name = name;
            this.age = age;
            this.className = className;
        }
    }

    // Phương thức in toàn bộ mảng sinh viên
    static void printStudentArray(Student[] students) {
        for (int i = 0; i < students.length; i++) {
            System.out.println("Index " + i + ": " + students[i].name + ", Age: " + students[i].age);
        }
    }

    // Phương thức tìm kiếm sinh viên theo tên và in thông tin
    static void searchAndPrintStudent(Student[] students, String targetName) {
        for (Student student : students) {
            if (student.name.equals(targetName)) {
                System.out.println(
                        "Found Student: " + student.name + ", Age:" + student.age + ",Class: " + student.className);
                return; // Thoát khỏi vòng lặp khi tìm thấy sinh viên
            }
        }
        System.out.println("Student not found: " + targetName);
    }

    // Phương pháp tìm học sinh lớn tuổi nhất và in thông tin
    static void printOldestStudent(Student[] students) {
        int maxAge = Integer.MIN_VALUE;
        Student oldestStudent = null;
        for (Student student : students) {
            if (student.age > maxAge) {
                maxAge = student.age;
                oldestStudent = student;
            }
        }
        System.out.println("Oldest Student: " + oldestStudent.name + ", Age: " + oldestStudent.age + ", Class: "
                + oldestStudent.className);
    }

    // Phương pháp hoán đổi sinh viên theo chỉ số cho trước trong mảng
    static void swapStudents(Student[] students, int index1, int index2) {
        if (index1 >= 0 && index1 < students.length && index2 >= 0 && index2 < students.length) {
            Student temp = students[index1];
            students[index1] = students[index2];
            students[index2] = temp;

        }
    }

    public static void main(String[] args) {
        // 1.Create an array of lists
        Student[] studentArray = new Student[4];

        // 2. Add students to the array by index as above
        studentArray[0] = new Student("Nguyen Van A", 10, "5D4");
        studentArray[1] = new Student("Nguyen Van B", 9, "4C3");
        studentArray[2] = new Student("Nguyen Van D", 8, "3B2");
        studentArray[3] = new Student("Nguyen Van D", 7, "2A1");

        // 3. Print the entire student list to the screen
        System.out.println("Student List:");
        printStudentArray(studentArray);

        // 4. Search for a student named Nguyen Van A ana print that student's
        // imformation
        System.out.println("\nSearching for Nguyen Van A:");
        searchAndPrintStudent(studentArray, "Nguyen Van A");

        // 5. Find the oldest student and print it to the screen
        System.out.println("\nOldest Student:");
        printOldestStudent(studentArray);

        // 6. Swap student index 0 wwith Index 3, Reprint the array
        swapStudents(studentArray, 0, 3);
        System.out.println("\nAfter Swapping Students:");
        printStudentArray(studentArray);

    }
}
