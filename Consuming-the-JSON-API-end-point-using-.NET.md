osTicket has an HTTP based API end point that can accept JSON payloads (apart from the other end point that accepts XML). This page gives an idea of how to file new tickets using .NET (in a language independent manner) into your osTicket instance. The information given here is based off of [https://colab.interlegis.leg.br/browser/osTicket-1.7/setup/doc/api/tickets.md](https://colab.interlegis.leg.br/browser/osTicket-1.7/setup/doc/api/tickets.md).

Az osTicket HTTP alapú API végpontja, amely elfogadhatja a JSON hasznos terheket (az XML-t elfogadó másik végponttól eltekintve). Ez az oldal ötletet ad arról, hogyan kell új jegyeket feltölteni a .NET segítségével (nyelvileg független módon) az osTicket példányba. Az itt megadott információ a [https://colab.interlegis.leg.br/browser/osTicket-1.7/setup/doc/api/tickets.md](https://colab.interlegis.leg.br/browser/osTicket-1.7/setup/doc/api/tickets.md).

## The JSON Structure

The file below represents an example payload that can be sent to the API.

Az alábbi fájl példaként szolgál az API-nak elküldhető hasznos tartalomnak.

```
{
    "name": "Angry User",
    "email": "api@osticket.com",
    "phone": "3185558634X123",
    "subject": "Testing API",
    "ip": "123.211.233.122",
    "message": "MESSAGE HERE",
    "topicId": "1",
    "attachments": [
        {"image.png": "data:image/png;base64,R0lGODdhMAA..."},
    ]
}
```

## Libraries Needed
You will not need much in order to encode the JSON payload and send it to the osTicket API end point. In fact you will need to use the .NET base class libraries (namely mscorlib.dll and System.dll) together with the JSON.NET library. The latter can be obtained by downloading the ```Newtonsoft.Json``` package from NuGet.org using your favourite NuGet client.

Nem szükséges sok ahhoz, hogy kódolhassa a JSON hasznos terhet, és küldje el az osTicket API végpontjába. Valójában a .NET alap osztálykönyvtárakat (nevezetesen mscorlib.dll és System.dll) kell használni a JSON.NET könyvtárral együtt. Az utóbbit a NuGet.org "` Newtonsoft.Json`` csomagjának letöltésével szerezheti be a kedvenc NuGet kliens használatával.

## Steps Needed
The following steps highlight the method required for encoding and sending a ticket to the JSON API end point.

A következő lépések kiemelik a jegy kódolásához és küldéséhez szükséges módszert a JSON API végpontjához.

* Import the System, System.Net, Newtonsoft.Json and System.Collections.Generic namespaces
* Make a ```Dictionary<string, object>``` instance, and name it ```payload``
* Use the ```Add``` method on the ```payload``` dictionary to add key value pairs for all the attributes in the desired JSON. Leave out the ```attachments``` key value pair for now.
* Make a new ```Dictionary<string,string>``` instance named ```atts```.
* Add key value pairs to ```atts``` with the key being the file name and the value being a data URL string with the file. (A data URL string would be produced by putting the file mime type and the file's Base64 encoding into the following template: ```data:{{mime}};base64,{{base64}}```.
* Add the entry with ```attachments``` being the key and a ```Dictionary<string,string>``` array having ```atts``` as its only element as the value to the ```payload``` dictionary.
* Now to send it, make a ```WebClient``` instance named ```client```.
* Add the following headers to the ```client.Headers``` collection using its ```Add``` method:
    * "X-API-Key", "YOUR API KEY HERE"
    * "Expect", ```string.Empty```
    * "User-Agent", "My osTicket Client"
* Next, encode the ```payload``` using JSON.NET by calling ```JsonConvert.SerializeObject(payload)``` and putting the result in a new ```string`` variable named ```json```.
* Finally send the request using ```client.Upload("http://yourdomain.tld/api/http.php/tickets.json", "POST", json)```.