# Day-24
def add_student(records, name, age, grade):
    student = {"name": name, "age": age, "grade": grade}
    records.append(student)
    return records

def display_students(records):
    for i, student in enumerate(records, 1):
        print(f"{i}. Name: {student['name']}, Age: {student['age']}, Grade: {student['grade']}")

def export_to_csv(records, filename='students.csv'):
    import csv
    with open(filename, 'w', newline='') as file:
        writer = csv.DictWriter(file, fieldnames=["name", "age", "grade"])
        writer.writeheader()
        writer.writerows(records)
    print(f"Exported to {filename}")

if __name__ == "__main__":
    students = []
    students = add_student(students, "Ali", 21, "A")
    students = add_student(students, "Sara", 22, "B")
    display_students(students)
    export_to_csv(students)
