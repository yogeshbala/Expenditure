const form = document.getElementById('expense-form');
const expenseList = document.getElementById('expense-list');
const totalDisplay = document.getElementById('total');

let expenses = JSON.parse(localStorage.getItem('expenses')) || [];

function updateExpenses() {
    expenseList.innerHTML = '';
    let total = 0;

    expenses.forEach((expense, index) => {
        const li = document.createElement('li');
        li.innerHTML = `${expense.name} - ₹${expense.amount} - ${expense.date} 
            <button onclick="deleteExpense(${index})">❌</button>`;
        expenseList.appendChild(li);
        total += parseFloat(expense.amount);
    });

    totalDisplay.textContent = total.toFixed(2);
    localStorage.setItem('expenses', JSON.stringify(expenses));
}

function deleteExpense(index) {
    expenses.splice(index, 1);
    updateExpenses();
}

form.addEventListener('submit', (e) => {
    e.preventDefault();

    const name = document.getElementById('expense-name').value;
    const amount = document.getElementById('expense-amount').value;
    const date = document.getElementById('expense-date').value;

    expenses.push({ name, amount, date });
    updateExpenses();

    form.reset();
});

updateExpenses();