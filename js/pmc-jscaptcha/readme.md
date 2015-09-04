PMC JCaptcha
===================

**PMC JCaptcha** is a pure Javascript implementation of captcha/challenge question. Its not as secure/foolproof as the regular captcha implementations because the validation in this one happens on the client side itself in Javascript but its ideal for cases where server-end validation is not feasible for one reason or the other.

This library generates random mathematical questions for addition or multiplication of 2 random numbers and provides an API to get the question and to verify if an answer is correct or not.

**Important :** This library supports only one question per object. If you want to have multiple challenge questions on a single page then you will need to create a new object of `PMC_JCaptcha` class for each question and answer to a question can be verified only via the object through which the question was generated.

#### **Usage Example:**

```javascript
//Display challenge question inside '#captcha-question' element
jQuery( '#captcha-question' ).text( pmc_jcaptcha.get_question() + ' = ' );

//Let's check for captcha answer before #form-a is submitted
jQuery( '#form-a' ).on( 'submit', function() {
	var captcha_value = jQuery( '#captcha-answer' ).val();
	
	if ( pmc_jcaptcha.is_answer( captcha_value ) ) {
		//Its ok to submit form
		return true;
	}

	//Show some error
	//Don't submit form
	return false;
} );
```

The usage example above uses jQuery for manipulating DOM (to display challenge question and get answer input by user) but the **PMC JCaptcha** library itself has no external dependencies and it can work with any Javascript library/framework etc.
