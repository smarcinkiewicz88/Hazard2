# Hazard2

krupier musi dobrać d 17, jesśli ma 21 wygrywa, jeśli ma więcej niż 21 to wszyscy przy stole wygrywają
jesłi gracz ma więcej niż 21 odrazu przegrywa

na początku grry kurupier dobiera jedną karę a gracz dostaje dwie

# Początek

Gracz na początku może poprosić o dobranie 1 karty


# Wartości kart
  - as 1 lub 11
  - król 10
  - dama 10
  - walet 10
  - dalej zgodnie z warościami kart

  - import tkinter as tk
from tkinter import ttk
from PIL import Image, ImageTk

def save_form():
    name = entry_name.get()
    email = entry_email.get()
    gender = gender_var.get()
    education = education_var.get()
    rating = spinbox_rating.get()

    if not name or name == "Proszę podać imię i nazwisko":
        result_label.config(text="Proszę wypełnić pole 'Imię i nazwisko'.")
        return

    result_text = (f"Imię i nazwisko: {name}\n"
                   f"Adres email: {email}\n"
                   f"Płeć: {gender}\n"
                   f"Wykształcenie: {education}\n"
                   f"Ocena jakości obsługi: {rating}")
    result_label.config(text=result_text)

# Główne okno aplikacji
root = tk.Tk()
root.title("Ankieta zadowolenia klienta")
root.geometry("500x400")
root.configure(bg="#D4D9DB")

# Nagłówek
header = tk.Label(root, text="Ankieta zadowolenia klienta", font=("Times New Roman", 18, "bold"), fg="blue", bg="#D4D9DB")
header.pack(pady=10)

# Zdjęcie
try:
    image = Image.open("klient.jpg")
    image = image.resize((100, 100))
    photo = ImageTk.PhotoImage(image)
    img_label = tk.Label(root, image=photo, bg="#D4D9DB")
    img_label.pack(pady=5)
except Exception as e:
    img_label = tk.Label(root, text="Brak zdjęcia klienta", bg="#D4D9DB")
    img_label.pack(pady=5)

# Formularz
form_frame = tk.Frame(root, bg="#D4D9DB")
form_frame.pack(pady=10)

# Pole Imię i nazwisko
label_name = tk.Label(form_frame, text="Imię i nazwisko:", bg="#D4D9DB")
label_name.grid(row=0, column=0, sticky="w")
entry_name = tk.Entry(form_frame, width=30)
entry_name.insert(0, "Proszę podać imię i nazwisko")
entry_name.grid(row=0, column=1, padx=10, pady=5)

# Pole Adres email
label_email = tk.Label(form_frame, text="Adres email:", bg="#D4D9DB")
label_email.grid(row=1, column=0, sticky="w")
entry_email = tk.Entry(form_frame, width=30)
entry_email.grid(row=1, column=1, padx=10, pady=5)

# Pole płci (radio buttons)
gender_var = tk.StringVar(value="")
label_gender = tk.Label(form_frame, text="Płeć:", bg="#D4D9DB")
label_gender.grid(row=2, column=0, sticky="w")
frame_gender = tk.Frame(form_frame, bg="#D4D9DB")
frame_gender.grid(row=2, column=1, sticky="w")

tk.Radiobutton(frame_gender, text="Mężczyzna", variable=gender_var, value="Mężczyzna", bg="#D4D9DB").pack(side="left")
tk.Radiobutton(frame_gender, text="Kobieta", variable=gender_var, value="Kobieta", bg="#D4D9DB").pack(side="left")

# Lista rozwijalna (wykształcenie)
label_education = tk.Label(form_frame, text="Wykształcenie:", bg="#D4D9DB")
label_education.grid(row=3, column=0, sticky="w")
education_var = tk.StringVar(value="Podstawowe")
education_dropdown = ttk.Combobox(form_frame, textvariable=education_var, state="readonly",
                                   values=["Podstawowe", "Zawodowe", "Średnie", "Wyższe"])
education_dropdown.grid(row=3, column=1, padx=10, pady=5)

# Pole numeryczne (ocena jakości obsługi)
label_rating = tk.Label(form_frame, text="Jak oceniasz jakość obsługi:", bg="#D4D9DB")
label_rating.grid(row=4, column=0, sticky="w")
spinbox_rating = tk.Spinbox(form_frame, from_=0, to=6, width=5)
spinbox_rating.grid(row=4, column=1, padx=10, pady=5, sticky="w")

# Przycisk Zapisz
save_button = tk.Button(root, text="Zapisz", command=save_form, bg="red", fg="white")
save_button.pack(pady=10)

# Wynik
result_label = tk.Label(root, text="", bg="#D4D9DB", justify="left")
result_label.pack(pady=10)

root.mainloop()



....
import java.util.Scanner;

public class EvenSumCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Get the number of elements from the user
        System.out.print("Enter the number of elements: ");
        int n = scanner.nextInt();
        int[] array = new int[n];

        // Read elements into the array
        System.out.println("Enter " + n + " numbers:");
        for (int i = 0; i < n; i++) {
            array[i] = scanner.nextInt();
        }

        // Calculate the sum of even numbers
        int sum = calculateEvenSum(array);

        // Display the result
        System.out.println("Sum of even numbers: " + sum);

        scanner.close();
    }

    // Method to calculate the sum of even numbers in an array
    public static int calculateEvenSum(int[] arr) {
        int sum = 0;
        for (int num : arr) {
            if (num % 2 == 0) {
                sum += num;
            }
        }
        return sum;
    }
}


