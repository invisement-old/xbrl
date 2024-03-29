
### Financial Data Extractor
Extract financial tags from xml, SEC submissions, xlbr, xlbri, or html

https://extract.invisement.com/

##### Demo


<center>
<form enctype="multipart/form-data" method='post' action='/extract-xml'>
    <input type='radio' name='input_type' value='url' checked> url to extract: <input name='url' type='url'> <br>
    <input type='radio' name='input_type' value='file'> file to extract: <input name='file' type='file'> <br>
    output
    <select name='output'>
        <option type='radio' value='json' selected>json</option>
        <option type='radio' value='csv'>csv</option>
    </select><br>
    <input type='submit'><br>
    Enter url or fila path to the xml document that you want to extract its financial tags.
</form>
</center>


##### how to `get` it through browser?
if you have the url to your file:
https://extract.invisement.com/extract-xml?url=your-url

example: https://extract.invisement.com/extract-xml?url=https://www.sec.gov/Archives/edgar/data/1000045/0001564590-19-031992.txt


```js
// in js:
fetch(https://extract.invisement.com/extract-xml?url=your-url).then(function(tags){
    //do something with tags
})
// in python:
import pandas as pd
tags = pd.read_csv(https://extract.invisement.com/extract-xml?url=your-url)
```

##### How to get it in csv
Add `&output=csv` to the end of your query.

example: https://extract.invisement.com/extract-xml?url=https://www.sec.gov/Archives/edgar/data/1000045/0001564590-19-031992.txt&output=csv


##### how to use it with google sheets or Excel
Technically, you can import the above csv url in most of application including google-sheets, excel, apple numbers, power-bi, tableau, data-studio, etc.

For google-sheets, in a cell write formula `=importdata(https://extract.invisement.com/extract-xml?url=your-url&output=csv)`

In a similar way, in Excel you can use `data > Import Text File` with comma delimiter and instead of file provide the above url. You can also import it through 


##### how to use the library
The extractor is written in python. Download file "extract_xbrl.py" to your project and then

```py
import extract_xbrl as xbrl, requests
xml_text = requests.get(url_to_xml_doc).content
tags = xbrl.Extract(xml_text)
```

</body>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/skeleton/2.0.4/skeleton.min.css" />

<style>
    form{border: 1px outset; padding: 1em; max-width: 30em; display: inline-block;}
    html{margin: auto; padding: 1em; max-width: 90em; border: 1px outset; color:black;}
</style>


</html>




