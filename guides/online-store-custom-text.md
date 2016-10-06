# Customize text during store checkout

## Checkout page

### Auto expand message field and change description

```js
$('#add_message_button').click();
$('#message_area label').text('Which engraving do you want?');
$('#message_area textarea').attr('placeholder', 'I.e. Your Name');
```

### Change buy button to rent

```js
$('.cart_add button').text('Rent');
Shop.texts.toCheckout = 'Make reservation';

// Thanks
$('.checkout > h1').text('Thanks for your reservation');
$('.checkout > h1 + p').append('We will get back to your with a confirmation');

// Checkout
$('.checkout form h1').text('Your rental');
$('#payment h3').text('Pay');
$('#payment_button button').text('Send request');
```

