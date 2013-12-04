FormValidation
==============

A class to import to use for Forms field validation

Example of how to use it :

```android
ArrayList<Boolean> formValidation = new ArrayList<Boolean>();

formValidation.add(FormValidation.validationSetError(EDITTEXT_NAME.getText().toString(), FormValidation.NAME, EDITTEXT_NAME));
formValidation.add(FormValidation.validationSetError(EDITTEXT_PASSWORD.getText().toString(), FormValidation.PW, EDITTEXT_PASSWORD));
formValidation.add(FormValidation.validationSetError(EDITTEXT_EMAIL.getText().toString(), FormValidation.EMAIL_COMPULSORY, EDITTEXT_EMAIL));

//IF validation passes all fields
if (!formValidation.contains(false)) {
	//DO SOMETHING
}
```
Field checks include :

```android
NAME
IC
PW
CFM_PW
EMAIL_COMPULSORY
EMAIL
PHONE_COMPULSORY
PHONE
POSTAL_COMPULSORY (6 digits)
POSTAL (6 digits)
HOME_UNIT_COMPULSORY
DATE_COMPULSORY (dd/MM/yyyy format)
DATE (dd/MM/yyyy format)
CASH_AMOUNT_COMPULSORY
CASH
```

Class allows users to create and add their own validation fields with 2 additional methods :

1. validate_compulsory (when field requires mandatory input)

```android
String validate_compulsory(String validate_string, String regex, String error_blank, String error_extra)
```

That takes in parameters { String validate_string, String regex, String error_blank, String error_extra }
- validate_string : String from EditText to be validated
- regex : String regular expression to check
- error_blank : String error message when field is blank
- error_extra : String error message when field does not match regular expression

Hence this has to be called :

```android
formValidation.add(FormValidation.validationSetError_custom_compulsory(EDITTEXT_CUSTOM.getText().toString(), REGEX, "Error message blank", "Error message dont match", EDITTEXT_CUSTOM));
```

2. validate (when field does not require mandatory input)

```android
String validate(String validate_string, String regex, String error_extra)
```

That takes in parameters { String validate_string, String regex, String error_extra }
- validate_string : String from EditText to be validated
- regex : String regular expression to check
- error_extra : String error message when field does not match regular expression

Hence this has to be called :

```android
formValidation.add(FormValidation.validationSetError_custom(EDITTEXT_CUSTOM.getText().toString(), REGEX, "Error message dont match", EDITTEXT_CUSTOM));
```
