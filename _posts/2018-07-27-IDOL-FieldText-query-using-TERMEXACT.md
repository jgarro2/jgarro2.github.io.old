---
title: "IDOL FieldText query using TERMEXACT"
---

# IDOL FieldText query using TERMEXACT

**FieldText** is used to add a field restriction to a query. 

## TERMEXACT

The **TERMEXACT** field specifier (case sensitive) allows you to find documents with a  specified field that contains an exact match of any of the terms  specified by you. 

### Format

```IDOL Query
FieldText=TERMEXACT{yourTerms}:yourFields
```

#### `yourTerms` 

- Type one or more terms.
- A document is only returned if one of `yourFields` contains a value that exactly matches one of the specified terms. 
- You can match strings that contain punctuation or consist of several words. 

#### `yourFields`

- Type one or more fields. 
- A document is only returned if it contains one of these fields, and if this field contains an exact match of one of `yourTerms`. 
- Separate multiple fields with colons (:). 
- There must be no space before or after a colon.

**Note:** To distinguish query syntax punctuation from punctuation within strings,  double-percent-encode commas and curly braces within strings. Query  syntax punctuation must be left unencoded. There must be no space before or after a separator comma. 

###Example

FieldText=TERMEXACT{help,helped}:DRETITLE

- A document's DRETITLE field value must contain the term help or helped for this document to be returned. 
- If a document's DRETITLE field, for example, has the value helps or helping, the document is not returned.

http://h30359.www3.hpe.com/online_help/IDOL/Servers/IDOL%20Server/11.1/Help/index.html#Actions/Field%20Specifiers/_IDOL_TERMEXACT.htm?Highlight=termexact