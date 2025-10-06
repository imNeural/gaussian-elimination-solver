# Gaussian Elimination Calculator

[](https://opensource.org/licenses/MIT)
[](https://gaussian-elimination-solver.vercel.app/) A web application that solves systems of linear equations with a step-by-step visualization of the Gaussian elimination process. This tool is designed for students, educators, and professionals who need to understand the mechanics of this fundamental linear algebra algorithm.

**[Live Demo](https://gaussian-elimination-solver.vercel.app/)**  

# Features

  * **Step-by-Step Solution**: Visualizes the entire forward elimination and back substitution process, showing the row operations applied at each stage.
  * **Multiple Input Methods**: Enter your system of linear equations in either a standard matrix form `[A|B]` or as a list of equations (e.g., `3x + 2y = 7`).
  * **Variable Matrix Size**: Supports systems with 2 to 6 variables.
  * **Interactive UI**: A clean and responsive interface built with Tailwind CSS, featuring a dark/light mode toggle for user comfort.
  * **Educational Section**: Includes a detailed, collapsible "Learn" section that explains the theory behind Gaussian elimination, elementary row operations, and provides a worked example.
  * **Beautiful Math Rendering**: Uses KaTeX to display matrices and mathematical notations clearly and professionally.

## How It Works

The application consists of a static frontend and a serverless Python backend:

1.  **Frontend**: The user enters the system of equations into the `index.html` page. The interface is built with **HTML** and **Tailwind CSS**.
2.  **API Call**: Client-side **JavaScript** validates the input and sends it to a serverless backend endpoint (`/solve`) as a JSON payload.
3.  **Backend**: A **Python** backend using the **Flask** micro-framework receives the request.
4.  **Computation**: The backend uses the **NumPy** library to construct the augmented matrix and efficiently perform the Gaussian elimination algorithm. It carefully records the description and state of the matrix at each step.
5.  **Response**: The backend returns a detailed JSON object containing the step-by-step process and the final solution.
6.  **Display**: The frontend JavaScript parses the JSON response and dynamically renders the solution steps and the final answer in the browser.

## Technologies Used

  * **Frontend**: HTML, JavaScript, Tailwind CSS, KaTeX
  * **Backend**: Python, Flask, Flask-Cors
  * **Numerical Processing**: NumPy 
  * **Deployment**: Vercel

## Setup and Local Development

To run this project on your local machine:

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/imNeural/gaussian-elimination-solver.git
    cd gaussian-solver
    ```

2.  **Set up the Python backend:**

      * It's recommended to use a virtual environment:
        ```bash
        python -m venv venv
        source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
        ```
      * Install the required packages from `requirements.txt`:
        ```bash
        pip install -r requirements.txt
        ```
      * Run the Flask development server:
        ```bash
        flask --app api/app run
        ```

    The backend will now be running on `http://127.0.0.1:5000`.

3.  **Launch the frontend:**

      * Simply open the `index.html` file in your web browser. The JavaScript is configured to send requests to the backend.

## Deployment

This project is configured for seamless deployment on **Vercel**. The `vercel.json` file handles the build configuration and routing, automatically deploying the Flask app as a serverless function and serving the static frontend. Any push to the `main` branch on GitHub will trigger a new deployment.

## License

This project is licensed under the MIT License. See the [LICENSE](https://opensource.org/licenses/MIT) file for details.
