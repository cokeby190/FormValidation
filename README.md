FormValidation
==============

A class to import to use for Forms field validation

Example of how to use it :

ArrayList<Boolean> formValidation = new ArrayList<Boolean>();

formValidation.add(FormValidation.validationSetError(EDITTEXT_NAME.getText().toString(), FormValidation.NAME, EDITTEXT_NAME));
formValidation.add(FormValidation.validationSetError(EDITTEXT_PASSWORD.getText().toString(), FormValidation.PW, EDITTEXT_PASSWORD));
formValidation.add(FormValidation.validationSetError(EDITTEXT_EMAIL.getText().toString(), FormValidation.EMAIL_COMPULSORY, EDITTEXT_EMAIL));

//IF validation passes all fields
if (!formValidation.contains(false)) {
	//DO SOMETHING
}
