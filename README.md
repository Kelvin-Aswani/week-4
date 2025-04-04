# week-4
try:  
    with open("notes.txt", "w") as file:  
        file.write("Line 1: Today is a sunny day.\nLine 2: I am learning Python.\nLine 3: File handling is fun!")  
    with open("notes.txt", "r") as file:  
        print(file.read())  
except Exception as e:  
    print(f"Error: {e}")  
    try:  
    user_input = input("Enter a new line to append: ")  
    with open("notes.txt", "a") as file:  
        file.write(f"\n{user_input}")  
    with open("notes.txt", "r") as file:  
        print(file.read())  
except FileNotFoundError:  
    print("Error: File not found.")  
except Exception as e:  
    print(f"Error: {e}")  
finally:  
    print("File operations completed.")  
    def count_lines(filename):  
    try:  
        with open(filename, "r") as file:  
            lines = file.readlines()  
            return len(lines)  
    except FileNotFoundError:  
        print("Error: File not found.")  
        return -1  
    except PermissionError:  
        print("Error: Permission denied.")  
        return -1  
    except Exception as e:  
        print(f"Error: {e}")  
        return -1  

result = count_lines("notes.txt")  
if result != -1:  
    print(f"Number of lines: {result}")  
