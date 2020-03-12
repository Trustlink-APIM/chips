# API Marketplace Data Type

## Index
* Phone numbers


## Phone numbers
Phone numbers can occur in a number of formats and in different parts of an API call. 
For APIs in the Marketplace the format defaults to international format i.e. +\<countryCode\>\<number\>. For example a South African number would look like this +27821231234.

When a phone number is passed as a URL path parameter or query string parameter, it needs to be URL encoded. Most tools like the API Marketplace Try It feature, Postman, Stoplight etc will handle the encoding for you.

If you are passing the number via a raw url call in a tool like curl it needs to be url encoded thus the '+' should be '%2B', thus %2B27821231234 for the example above.
