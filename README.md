# progressive-json-response
Load/fetch JSON response chunk by chunk.

# Code Example

## Step 1 - HTML(before data load)

```HTML
<ol id="output">
</ol>
```

## Step 2 - Javascript

```javascript
var output = document.getElementById('output');

oboe('https://mysafeinfo.com/api/data?list=englishmonarchs&format=json')
    .node('nm', function(elem) {
        var li = document.createElement('li');
        li.innerHTML = 'My name is ' + elem;
        output.appendChild(li);
    })
    .node('cty', function(elem) {
        var lastChild = output.lastChild;
        lastChild.innerHTML = lastChild.innerHTML + '. I live in ' + elem;
    })
    .node('hse', function(elem) {
        var lastChild = output.lastChild;
        lastChild.innerHTML = lastChild.innerHTML + '. Stay at ' + elem;
    })
    .node('yrs', function(elem) {
        var lastChild = output.lastChild;
        lastChild.innerHTML = lastChild.innerHTML + '. My very sad and happy moment was last from ' + elem;

    })
    .done(function( data ) {
    	setTimeout( function () {
        	alert( 'Done load request from endpoint!!, see browser console for data view. This alert the actual response time was finished load. The list element showed at the page was loaded chunk by chunk instead of waiting the whole data finish fetched!!' );
        }, 2000);
        console.log( data );
    });
```

## Step 3 - HTML(During endpoint request), this data was loaded and rendered chunk by chunk asynchronously

```HTML
My name is Edmund lronside. I live in United Kingdom. Stay at House of Wessex. My very sad and happy moment was last from 1016
My name is Cnut. I live in United Kingdom. Stay at House of Denmark. My very sad and happy moment was last from 1016-1035
My name is Harold I Harefoot. I live in United Kingdom. Stay at House of Denmark. My very sad and happy moment was last from 1035-1040
My name is Harthacanut. I live in United Kingdom. Stay at House of Denmark. My very sad and happy moment was last from 1040-1042
My name is Edward the Confessor. I live in United Kingdom. Stay at House of Wessex. My very sad and happy moment was last from 1042-1066
My name is Harold II. I live in United Kingdom. Stay at House of Wessex. My very sad and happy moment was last from 1066
My name is William I. I live in United Kingdom. Stay at House of Normandy. My very sad and happy moment was last from 1066-1087
My name is William II. I live in United Kingdom. Stay at House of Normandy. My very sad and happy moment was last from 1087-1100
My name is Henry I. I live in United Kingdom. Stay at House of Normandy. My very sad and happy moment was last from 1100-1135
My name is Stephen. I live in United Kingdom. Stay at House of Blois. My very sad and happy moment was last from 1135-1154
My name is Henry II. I live in United Kingdom. Stay at House of Angevin. My very sad and happy moment was last from 1154-1189
My name is Richard I. I live in United Kingdom. Stay at House of Angevin. My very sad and happy moment was last from 1189-1199
My name is John. I live in United Kingdom. Stay at House of Angevin. My very sad and happy moment was last from 1199-1216
My name is Henry III. I live in United Kingdom. Stay at House of Plantagenet. My very sad and happy moment was last from 1216-1272
My name is Edward I. I live in United Kingdom. Stay at House of Plantagenet. My very sad and happy moment was last from 1272-1307
My name is Edward II. I live in United Kingdom. Stay at House of Plantagenet. My very sad and happy moment was last from 1307-1327
My name is Edward III. I live in United Kingdom. Stay at House of Plantagenet. My very sad and happy moment was last from 1327-1377
My name is Richard II. I live in United Kingdom. Stay at House of Plantagenet. My very sad and happy moment was last from 1377-1399
My name is Henry IV. I live in United Kingdom. Stay at House of Lancaster. My very sad and happy moment was last from 1399-1413
My name is Henry V. I live in United Kingdom. Stay at House of Lancaster. My very sad and happy moment was last from 1413-1422
My name is Henry VI. I live in United Kingdom. Stay at House of Lancaster. My very sad and happy moment was last from 1422-1461
My name is Edward IV. I live in United Kingdom. Stay at House of York. My very sad and happy moment was last from 1461-1483
My name is Edward V. I live in United Kingdom. Stay at House of York. My very sad and happy moment was last from 1483
My name is Richard III. I live in United Kingdom. Stay at House of York. My very sad and happy moment was last from 1483-1485
My name is Henry VII. I live in United Kingdom. Stay at House of Tudor. My very sad and happy moment was last from 1485-1509
My name is Henry VIII. I live in United Kingdom. Stay at House of Tudor. My very sad and happy moment was last from 1509-1547
My name is Edward VI. I live in United Kingdom. Stay at House of Tudor. My very sad and happy moment was last from 1547-1553
My name is Mary I. I live in United Kingdom. Stay at House of Tudor. My very sad and happy moment was last from 1553-1558
My name is Elizabeth I. I live in United Kingdom. Stay at House of Tudor. My very sad and happy moment was last from 1558-1603
My name is James I. I live in United Kingdom. Stay at House of Stuart. My very sad and happy moment was last from 1603-1625
My name is Charles I. I live in United Kingdom. Stay at House of Stuart. My very sad and happy moment was last from 1625-1649
My name is Commonwealth. I live in United Kingdom. Stay at Commonwealth. My very sad and happy moment was last from 1649-1653
My name is Oliver Cromwell. I live in United Kingdom. Stay at Commonwealth. My very sad and happy moment was last from 1653-1658
My name is Richard Cromwell. I live in United Kingdom. Stay at Commonwealth. My very sad and happy moment was last from 1658-1659
My name is Charles II. I live in United Kingdom. Stay at House of Stuart. My very sad and happy moment was last from 1660-1685
My name is James II. I live in United Kingdom. Stay at House of Stuart. My very sad and happy moment was last from 1685-1688
My name is William III. I live in United Kingdom. Stay at House of Orange. My very sad and happy moment was last from 1689-1694
My name is Anne. I live in United Kingdom. Stay at House of Stuart. My very sad and happy moment was last from 1702-1714
My name is George I. I live in United Kingdom. Stay at House of Hanover. My very sad and happy moment was last from 1714-1727
My name is George II. I live in United Kingdom. Stay at House of Hanover. My very sad and happy moment was last from 1727-1760
My name is George III. I live in United Kingdom. Stay at House of Hanover. My very sad and happy moment was last from 1760-1820
My name is George IV. I live in United Kingdom. Stay at House of Hanover. My very sad and happy moment was last from 1820-1830
My name is William IV. I live in United Kingdom. Stay at House of Hanover. My very sad and happy moment was last from 1830-1837
My name is Victoria. I live in United Kingdom. Stay at House of Hanover. My very sad and happy moment was last from 1837-1901
My name is Edward VII. I live in United Kingdom. Stay at House of Saxe-Coburg-Gotha. My very sad and happy moment was last from 1901-1910
My name is George V. I live in United Kingdom. Stay at House of Windsor. My very sad and happy moment was last from 1910-1936
My name is Edward VIII. I live in United Kingdom. Stay at House of Windsor. My very sad and happy moment was last from 1936
My name is George VI. I live in United Kingdom. Stay at House of Windsor. My very sad and happy moment was last from 1936-1952
My name is Elizabeth II. I live in United Kingdom. Stay at House of Windsor. My very sad and happy moment was last from 1952-
My name is Edward the Elder. I live in United Kingdom. Stay at House of Wessex. My very sad and happy moment was last from 899-925
My name is Athelstan. I live in United Kingdom. Stay at House of Wessex. My very sad and happy moment was last from 925-940
My name is Edmund. I live in United Kingdom. Stay at House of Wessex. My very sad and happy moment was last from 940-946
My name is Edred. I live in United Kingdom. Stay at House of Wessex. My very sad and happy moment was last from 946-955
My name is Edwy. I live in United Kingdom. Stay at House of Wessex. My very sad and happy moment was last from 955-959
My name is Edgar. I live in United Kingdom. Stay at House of Wessex. My very sad and happy moment was last from 959-975
My name is Edward the Martyr. I live in United Kingdom. Stay at House of Wessex. My very sad and happy moment was last from 975-978
My name is Ethelred II the Unready. I live in United Kingdom. Stay at House of Wessex. My very sad and happy moment was last from 978-1016
```

