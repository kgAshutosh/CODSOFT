let display = document.getElementById('display');
let buttons = document.querySelectorAll('button');
let currentInput = '';
let operator = '';
let firstOperand = '';
let secondOperand = '';

buttons.forEach(button => {
    button.addEventListener('click', () => {
        const value = button.textContent;

        if (value === 'C') {
            // Clear the display and reset variables
            currentInput = '';
            operator = '';
            firstOperand = '';
            secondOperand = '';
            display.value = '';
        } else if (value === '=') {
            // Perform calculation
            if (firstOperand && operator && currentInput) {
                secondOperand = currentInput;
                display.value = calculate(firstOperand, secondOperand, operator);
                currentInput = display.value;
                operator = '';
                firstOperand = '';
            }
        } else if (['+', '-', '*', '/'].includes(value)) {
            // Handle operator input
            if (currentInput) {
                firstOperand = currentInput;
                operator = value;
                currentInput = '';
            }
        } else {
            // Handle number and decimal input
            currentInput += value;
            display.value = currentInput;
        }
    });
});

function calculate(first, second, operator) {
    first = parseFloat(first);
    second = parseFloat(second);

    switch (operator) {
        case '+':
            return first + second;
        case '-':
            return first - second;
        case '*':
            return first * second;
        case '/':
            return second !== 0 ? first / second : 'Error';
        default:
            return '';
    }
}
