<script>
import { onMount } from 'svelte';

let name, creditCardNumber, expirationDate, cvv, dollar;
let errorMessages = [];

onMount(() => {
  const form = document.querySelector('form.donation-form');

  form.addEventListener('submit', (event) => {
    event.preventDefault();

    errorMessages = [];

    validateName();
    validateCreditCardNumber();
    validateExpirationDate();
    validateCVV();
    validateDollar();

    if (errorMessages.length > 0) {
      displayErrorMessages();
      return;
    }

    submitForm();
  });

  function validateName() {
    if (!name) {
      errorMessages.push('Please enter your name');
    }
  }

  function validateCreditCardNumber() {
    if (!creditCardNumber || creditCardNumber.length < 16) {
      errorMessages.push('Please enter a valid credit card number');
    }
  }

  function validateExpirationDate() {
    if (!expirationDate) {
      errorMessages.push('Please enter your credit card expiration date');
    }
  }

  function validateCVV() {
    if (!cvv || cvv.length < 3) {
      errorMessages.push('Please enter your credit card CVV');
    }
  }

  function validateDollar() {
    if (!dollar) {
      errorMessages.push('Please enter a donation amount');
    }
  }

  function displayErrorMessages() {
    const errorMessageElement = document.querySelector('.error-messages');
    errorMessageElement.textContent = errorMessages.join('\n');
    errorMessageElement.style.display = 'block';
  }

  function submitForm() {
    console.log('Submitting form...');
  }
});


</script>

<div class="popup">
    <form class="donation-form">
      <fieldset>
        <legend>Donate from here</legend>
  
        <div class="form-group">
          <label for="name" class="form-label">Name:</label>
          <input type="text" id="name" class="form-control" on:input={(event) => name = event.detail.value} required />
        </div>
  
        <div class="form-group">
          <label for="creditCardNumber" class="form-label">Credit Card Number:</label>
          <input
            type="number"
            id="creditCardNumber"
            class="form-control"
            on:input={(event) => creditCardNumber = event.detail.value}
            required
          />
        </div>
  
        <div class="form-group">
          <label for="expirationDate" class="form-label">Expiration Date:</label>
          <input
            type="date"
            id="expirationDate"
            class="form-control"
            on:input={(event) => expirationDate = event.detail.value}
            required
          />
        </div>
  
        <div class="form-group">
          <label for="cvv" class="form-label">CVV:</label>
          <input type="number" id="cvv" class="form-control" on:input={(event) => cvv = event.detail.value} required />
        </div>
      </fieldset>
  
      <div class="form-group">
        <label for="option" class="form-label">Select an option:</label>
        <select id="option" class="form-select" on:input={(event) => dollar = event.detail.value} required>
          <option value="1">1</option>
          <option value="2">2</option>
          <option value="3">3</option>
        </select>
      </div>
  
      <div class="form-group">
        <label for="dollar" class="form-label">Donation Amount ($):</label>
        <input type="number" id="dollar" class="form-control" on:input={(event) => dollar = event.detail.value} required />
      </div>
  
      <div class="error-messages" style="display: none;"></div>
  
      <button type="submit" class="form-btn">Donate</button>
    </form>
  </div>

<style>
.popup {
position: fixed;
top: 0;
left: 0;
width: 100%;
height: 100%;
background-color: rgba(0, 0, 0, 0.7);
color: #000000;
display: flex;
align-items: center;
justify-content: center;
display:none;
}

  /* Form styles */

.donation-form {
width: 500px;
background-color: #fff;
padding: 20px;
border-radius: 10px;
}

.form-group {
margin-bottom: 10px;
}

.form-label {
display: block;
margin-bottom: 5px;
}

.form-control {
width: 100%;
padding: 10px;
border: 1px solid #ccc;
border-radius: 5px;
}

.form-control:valid {
border-color: green;
}

.form-select {
width: 100%;
padding: 10px;
border: 1px solid #ccc;
border-radius: 5px;
}

.form-btn {
display: block;
width: 100%;
padding: 10px 20px;
background-color: #007bff;
color: #fff;
border: none;
border-radius: 5px;
cursor: pointer;
}

@media (max-width: 576px) {
.popup {
width: 100%;
max-width: unset;
}
}

.donation-form fieldset {
border: 1px solid #ccc;
border-radius: 5px;
padding: 10px;
margin-bottom: 20px;
}
legend {
font-size: 18px;
font-weight: bold;
padding: 5px;
background-color: #f2f2f2;
border: 1px solid #ccc;
border-radius: 5px;
}

label {
display: block;
margin-bottom: 5px;
}
</style>