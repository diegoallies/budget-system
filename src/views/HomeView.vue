<template>
  <div class="home">

    <h1>Budget System</h1>

<div class="wrapper">
    <div id="field">
      <h2>Expenses</h2>
      <input type="text" name="expense-name" class="field" size="50" placeholder="Expense Name">
      <input type="number" name="expense-amount" class="fielde" size="50" placeholder="Expense Amount" value="">
      <!-- <input type="text" class="form-control" id="exampleInputEmail1" placeholder="answer"> -->
      <!-- <input type="text" @blur="handleBlur(post.amount)" class="form-control" id="exampleInputEmail1" v-model="post.amount" placeholder="Ingresa el monto"> -->


    </div>
    <div class="controls">
      <a href="#" id="add_more_fields" @click="add_more_fields()" ><i class="fa fa-plus"></i>Add More</a>
      <a href="#" id="remove_fields"><i class="fa fa-plus"></i>Remove Field</a>

       <div class="addItem">
        Add expense: <input type="text" id="newExpenseSource" placeholder="Source">
        <input type="text" id="newExpenseSum" placeholder="Sum">
        <select id="isNecessary">
            <option>Necessary</option>
            <option>Optional</option>
        </select>
        <button @click="getNewExpense()">Add</button>
<!-- /// -->

    <div class="categories">

        <div class="column" id="income">
            <h2 class="smallTitle">Incomes</h2>
            <table id="incomeTable">
                <td>Name</td>
                <td>Sum</td>
            </table>
        </div>

        <div class="column" id="expense">
            <h2 class="smallTitle">
                Expenses
            </h2>

            <table id="expensesTable">
                <td>Name</td>
                <td>Sum</td>
                <td>Necessity</td>
            </table>
        </div>   
    </div>
        <!-- /// -->
    </div>

    </div>
  </div>


  </div>
</template>

<script>
// @ is an alias to /src

export default {
  // name: 'HomeView',
  // components: {
  //   HelloWorld
  // }

  methods: {

  add_more_fields(){

  let expenseName = document.createElement('input');
  expenseName.setAttribute('type','text');
  expenseName.setAttribute('name','expense-name');
  expenseName.setAttribute('class','field');
  expenseName.setAttribute('width', 50);
  expenseName.setAttribute('placeholder','Expense Name');
  field.appendChild(expenseName);

  let expenseAmount = document.createElement('input');
  expenseAmount.setAttribute('type','number');
  expenseAmount.setAttribute('name','expense-name');
  expenseAmount.setAttribute('class', `${className}`);
  expenseAmount.setAttribute('id','fielde')
  expenseAmount.setAttribute('width', 50);
  expenseAmount.setAttribute('placeholder','Expense Amount');
  field.appendChild(expenseAmount);

},

  
    addExpenseToTable() {
           var table = document.getElementById("expensesTable");
           var row = table.insertRow(index_expense);
           row.id = 'row_id'+String(index_expense)
           var cell1 = row.insertCell(0);
           var cell2 = row.insertCell(1); 
           var cell3 = row.insertCell(2); 
           var cell4 = row.insertCell(3);
           cell1.innerHTML = name_expenses[name_expenses.length - 1];
           cell2.innerHTML = sum_expenses[sum_expenses.length - 1];
           cell3.innerHTML = expense_necessity[expense_necessity.length - 1];
           cell4.innerHTML = '<button onclick="removeItemExpense('+String(index_expense)+')">X</button>';
           index_expense += 1;
       },

       getNewExpense() {
     let name_expenses = [];
          let sum_expenses = [];
                 let expense_necessity = [];
                        let index_expense = 1;



           if (isNaN(document.getElementById("newExpenseSum").value)){
               alert("The sum you entered is not a number! Please enter a valid value!");
           }
           else {
               name_expenses.push(document.getElementById("newExpenseSource").value);
               sum_expenses.push(document.getElementById("newExpenseSum").value);
               expense_necessity.push(document.getElementById("isNecessary").value);
               addExpenseToTable();
           }

       },

// handleBlur() {
//     this.total_inputs = this.posts.reduce((totalAmount, post) => totalAmount + post.amount, 0);
// }




//  remove_fields(input_tags){
//   let input_tags = survey_options.getElementsByTagName('input');
//   if(input_tags.length > 2) {
//     survey_options.removeChild(input_tags[(input_tags.length) - 1]);
//   }
// }
  }
  
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Jost:wght@100;300;400;700&display=swap');

body {
  background-color: #f0f5ff;
  font-family: 'Jost',sans-serif;
  color: #fff;
}

.wrapper {
  width: 800px;
  margin: 40px auto;
  padding: 10px;
  border-radius: 5px;
  background: white;
  box-shadow: 0px 10px 40px 0px rgba(47,47,47,.1);
}

input[type="text"] {
  padding: 10px;
  margin: 10px auto;
  display: inline-block;
  border-radius: 5px;
  border: 1px solid lightgrey;
  background: none;
  width: 274px;
  color: black;
}

input[type="text"]:focus {
  outline: none;
}

.controls {
  width: 294px;
  margin: 15px auto;
}

#remove_fields {
  float: right;
}
.controls a i.fa-minus {
  margin-right: 5px;
}

a {
  color: black;
  text-decoration: none;
}

h1 {
  text-align: center;
  font-size: 48px;
  color: #232c3d;
}
</style>
