# Palindrome Checker  

You can access the checker here in the link below:
https://fadliazharr.github.io/Palindrome-checker/

## Overview  

This is a simple **Palindrome Checker** built using **HTML, CSS, and JavaScript**. It allows users to enter a word or phrase and checks whether it reads the same **forwards and backwards**, ignoring spaces, punctuation, and capitalization.  

## Features  

- Checks if a word or phrase is a palindrome  
- Ignores case, spaces, and special characters  
- User-friendly interface with real-time validation  
- Lightweight and fast  

## How It Works  

1. **User Input:**  
   - The user types a word or phrase into the input box.  
   - Clicking the **"Check" button** runs the palindrome test.  

2. **Processing the Input:**  
   - The script removes **non-alphanumeric characters** (like spaces and punctuation).  
   - It converts everything to **lowercase** to ensure case insensitivity.  
   - The cleaned-up text is compared to its **reversed version**.  

3. **Displaying the Result:**  
   - If the original and reversed text match, it displays "is a palindrome."  
   - If they do not match, it displays "is not a palindrome."  

## Code Explanation  

### **JavaScript Logic**  

The main logic runs when the button is clicked:  

```js
document.getElementById("check-btn").addEventListener("click", function() {
  const input = document.getElementById("text-input").value.trim();
  const resultElement = document.getElementById("result");

  if (input === "") {
    alert("Please input a value");
    return;
  }

  const formattedInput = input.replace(/[^a-zA-Z0-9]/g, "").toLowerCase();
  const reversedInput = formattedInput.split("").reverse().join("");

  if (formattedInput === reversedInput) {
    resultElement.textContent = `${input} is a palindrome`;
  } else {
    resultElement.textContent = `${input} is not a palindrome`;
  }
});
```

### **How it Works:**  

- **Trims whitespace** and ensures the input is not empty.  
- **Removes special characters** using a regular expression (`/[^a-zA-Z0-9]/g`).  
- **Converts to lowercase** to ensure a case-insensitive check.  
- **Reverses the string** and compares it to the original.  

### **Styling (CSS)**  

The interface is designed to be **simple and elegant**:  

- **Centered layout** for a clean look.  
- **Modern button design** with hover effects.  
- **Light and dark contrast** for readability.  

Example:  

```css
.container {
  text-align: center;
  background: white;
  padding: 20px 40px;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

#check-btn {
  background-color: #007bff;
  color: white;
  cursor: pointer;
}
```

## Expected Output  

| Input        | Output                     |
|-------------|----------------------------|
| **madam**    | "madam is a palindrome" |
| **racecar**  | "racecar is a palindrome" |
| **hello**    | "hello is not a palindrome" |
| **Was it a car or a cat I saw?** | "Was it a car or a cat I saw? is a palindrome" |
| **12321**    | "12321 is a palindrome" |

## How to Run  

1. Download the project files.  
2. Open `index.html` in a browser.  
3. Enter a word or phrase and click **Check**.  

## Possible Enhancements  

- Add **real-time validation** while typing.  
- Support **multilingual input** for wider usability.  
- Implement a **dark mode toggle** for better UX.  
