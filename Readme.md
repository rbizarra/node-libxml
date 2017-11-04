Node-LibXML
==========

LibXML2 Node.js Wrapper to Check: Wellformed, Validity against DTD, get doctype & getXpath elements

## Requirements: 

Node-Libxml has nos any dependencies, it's fully bundled, so you can just use it as it comes :)
Works on : Linux, Osx & Windows 
Node: Already built for all LTS node (4,6,8)

## Install

```bash
  npm i node-libxml
```

## Use

```javascript
  const Libxml = require('node-libxml');
  let libxml = new Libxml();

  // load function return true if wellformed, false if not
  // Info: if xml is not wellformed a property 'wellformedErrors'(array) containing a list of all errors will be set
  let xmlIsWellformed = libxml.load('path/to/xml');
  console.log(xmlIsWellformed);
  console.log(xmlIsWellformed.wellformedErrors);


  // load dtd & valid against it return true if valid, false if not, debug option is a boolean to set debug to true or not | default is false
  // Info: if xml is not wellformed a property 'validationErrors'(array) containing a list of all errors will be set
  let xmlIsValid = libxml.validateAgainstDtd('path:to/dtd',debug);
  console.log(xmlIsValid);
  console.log(xmlIsValid.validationErrors);


  // getDtd() return an object containing DTD info:  { "name": "article","externalId": "my doctype of doom","systemId": "mydoctype.dtd"}
  // Info: systemID could be a publicId too
  let dtdFile = libxml.getDtd();

  //Get some xpaths;
  let aRandomPathBoolean = libxml.xpathSelect('boolean(//some/path'));
  let aRandomPathNumber = libxml.xpathSelect('number(//some/path'));
  let countSomeElements = libxml.xpathSelect('count(//some/path'));
  //... & all xpath could do I think
```
