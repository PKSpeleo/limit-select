# LimitSelect

Online: [LimitSelect Demo](https://pkspeleo.github.io/limit-select)

A simple web application implementing a **limited selection with automatic deselection** principle. This application allows users to select items from a list with a maximum limit, automatically deselecting the earliest selected items when the limit is exceeded. The state of the list—including the items, their selection statuses, and the maximum selection limit—is stored in the URL's query parameters, allowing users to share their configurations with others.

## Table of Contents

- [Demo](#demo)
- [Features](#features)
- [Principle Explained](#principle-explained)
- [How It Works](#how-it-works)
- [Usage](#usage)
- [Development](#development)
- [License](#license)
- [Contributing](#contributing)

## Demo

Check out the live demo: [LimitSelect Demo](https://pkspeleo.github.io/limit-select)

## Features

- **Limited Selection**: Set a maximum number of items that can be selected at once.
- **Automatic Deselection**: When the selection limit is exceeded, the earliest selected item is automatically deselected.
- **Dynamic List Management**: Add or remove items from the list on the fly.
- **State Preservation**: The entire state is encoded in the URL, allowing you to bookmark or share the link to preserve the current configuration.
- **Unicode Support**: Item names can include any characters, including Unicode characters like Cyrillic letters.

## Principle Explained

The application demonstrates the principle of **limited multiple selection with automatic deselection**. This principle is useful in scenarios where:

- Users can select multiple options, but only up to a certain limit.
- If the limit is exceeded, the system automatically deselects previously selected items to enforce the limit.
- This ensures that the selection remains within the allowed constraints without requiring manual deselection by the user.

**Use Cases:**

- **Online Forms**: Limiting the number of selectable options in surveys or questionnaires.
- **Resource Allocation**: Managing limited resources by restricting the number of allocations.
- **Game Mechanics**: Enforcing rules where players can only choose a certain number of abilities or items.

## How It Works

- **Selection Limit**: Users can specify the maximum number of items that can be selected using a numerical input.
- **Item Management**: Users can add new items to the list or remove existing ones. Each item consists of a text input for the name and a checkbox for selection.
- **Automatic Deselection**: When the user selects more items than the maximum allowed, the application automatically deselects the earliest selected item(s) to maintain the limit.
- **State Encoding**: The application's state—including the list of items, their names, selection statuses, and the maximum selection limit—is serialized into a JSON string.
- **URL Query Parameters**: This JSON string is encoded using Base64 encoding with Unicode support and added to the URL as a query parameter.
- **State Restoration**: When the page is loaded, the application checks for the `state` parameter in the URL. If found, it decodes and parses the state to restore the application's previous configuration.

## Usage

1. **Access the Application**: Open the [LimitSelect Demo](https://pkspeleo.github.io/limit-select) in your web browser.

2. **Set Maximum Selection**:
    - Use the numerical input at the top to set the maximum number of items that can be selected.

3. **Add Items**:
    - Click the **Add Item** button to add a new item to the list.
    - Enter a name for the item in the text input field. You can use any characters, including Unicode characters like Cyrillic letters.

4. **Select Items**:
    - Use the checkboxes next to each item to select or deselect them.
    - The application will enforce the maximum selection limit, automatically deselecting the earliest selected items if necessary.

5. **Remove Items**:
    - Click the **Remove** button next to an item to delete it from the list.

6. **Share Your Configuration**:
    - Copy the URL from your browser's address bar.
    - Share this URL with others. When they open it, they will see the same list of items, selections, and maximum selection limit that you configured.

## Development

To run the application locally or contribute to its development:

1. **Clone the Repository**:

    ```bash
    git clone https://github.com/PKSpeleo/limit-select.git
    ```

2. **Navigate to the Directory**:

    ```bash
    cd limit-select
    ```

3. **Serve the Application**:

   For the application to work correctly (due to URL manipulation and local file access policies), you should serve it using a local web server.

    - **Using Python 3**:

        ```bash
        python -m http.server
        ```

      Then navigate to `http://localhost:8000` in your browser.

    - **Using Node.js (http-server)**:

        ```bash
        npm install -g http-server
        http-server
        ```

      Then navigate to the provided local address (e.g., `http://localhost:8080`).

    - **Using Live Server Extension (VS Code)**:

        - Install the **Live Server** extension in Visual Studio Code.
        - Open the project folder in VS Code.
        - Right-click `index.html` and select **Open with Live Server**.

4. **Modify the Code**:

    - The main functionality is implemented in the `index.html` file.
    - You can edit the HTML, CSS, and JavaScript directly in this file.
    - After making changes, refresh the page in your browser to see the updates.

5. **Contribute**:

    - **Report Issues**: If you find any bugs or have suggestions, please open an issue on GitHub.
    - **Pull Requests**: Feel free to fork the repository, make changes, and submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

## Contributing

Contributions are welcome! Please open an issue or submit a pull request on GitHub.

---
