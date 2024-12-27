# MonkeyType Automation with Selenium

This project automates typing on the [MonkeyType](https://monkeytype.com/) website using Selenium WebDriver. The script can type out text in different ways (e.g., letter-by-letter, word-by-word, etc.) at a custom delay. It also captures the results like words per minute (WPM), accuracy, and consistency.

## Requirements

- Python 3.11+
- Install required libraries via the `requirements.txt` file.

## Installation

1. Clone the repository:
   ```bash
   git clone <repo-link>
   ```

2. Navigate to the project directory:
   ```bash
   cd <folder-name>
   ```

3. Create a virtual environment:
   ```bash
   python -m venv venv
   ```

4. Activate the virtual environment:
   - For Windows:
     ```bash
     .\venv\Scripts\activate
     ```
   - For macOS/Linux:
     ```bash
     source venv/bin/activate
     ```

5. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. The script will open a browser window and navigate to [MonkeyType](https://monkeytype.com/).
2. It will attempt to accept cookies if the prompt appears.
3. After that, you can run one of the typing functions to automate typing:
   - `letterByLetter(delay)`: Types each letter one by one with a specified delay.
   - `allAtOnce(delay)`: Types all the letters of the current active word at once.
   - `wordByWord(delay)`: Types each word as a whole at the specified delay.
   - `wordLetterByLetter(delay)`: Types each word's letters individually, one after another.

   You can customize the `delay` parameter for each function to control typing speed.

4. Once the typing session is complete, the script will print the typing results: WPM (words per minute), accuracy, and consistency.

## Example

Run the script like this:

```python
delay = 0.001  # Set a small delay for fast typing
wordByWord(delay)
```

To check your typing statistics after finishing the test:

```python
wpm = browser.find_element(By.CSS_SELECTOR, ".group.wpm").find_element(By.CLASS_NAME, "bottom").text
acc = browser.find_element(By.CSS_SELECTOR, ".group.acc").find_element(By.CLASS_NAME, "bottom").text
consistency = browser.find_element(By.CSS_SELECTOR, ".group.flat.consistency").find_element(By.CLASS_NAME, "bottom").text

print("wpm: " + wpm)
print("accuracy: " + acc)
print("consistency: " + consistency)
```

## Troubleshooting

- If you encounter issues with stale elements, it may be due to dynamic content on the page. Ensure the page has fully loaded before interacting with elements.
- Make sure the `ChromeDriver` is correctly installed and compatible with your Chrome version. The `webdriver-manager` package should handle this automatically.

## Contributing

1. Fork the repository.
2. Create a new branch for your feature or fix.
3. Make your changes.
4. Open a pull request with a description of what you've done.
