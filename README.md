# Fed-Hams-QSL
 Federated/Distributed Ham Log Book


### Distributed Ham Log Book 

This is a more modern QSL and logbook manager. Allowing Digital QSLs to be created Shared and confirmed amo[Federated/Distributed Ham Log Book](https://github.com/users/humanpenguin/projects/1)ng multiple Federated Logbook managers around the Internet. 

The system will basically work like a Distributed Message List allowing Topics (Call Signs, Competitions, OTAs or Challenges) to be a identified in a QSL Topics section. Linked to Other QSLs by matching the contact data supplied. I.E. Call signs, Date, Time, Mode and Frequency.

Once Matched a confirmed version of the QSL is returned to the Originator and any system searching for QSL based on matching topics and or contact data. 

This will likely be done in python to allow cross platform installation, 

### QSL Originator Client (QOC until I think of a cooler name) 

This will be a cross platform (python) program running the Home PC of the QSL creator. 

Basically this client dose the Job of the Ham in older paper based QSL Card system. 

It creates a Digital QSL card blank. This consists of a simple limited HTML file/directory. Only images text tables and simple positioning based css data. This will be strictly limited to avoid worry of security risks. 

This is encrypted using pgp. And the public key is included in the open with the file. So anyone can read the data. And confirm the author is the person identified via that keSimple Name=Value csv _filey._ Any attempt to change the data can only be done by the private key owner. As the final confirmed Digital QSL will have contact data from both members of the conversation with different PGP keys. And server receiving an updThat will take logbook / QSL entries. Allow other servers to check the entries for matches with Eateries in there own submitted list link and confirm them. 

Updated card will fail to confirm a change card unless both parties submit matching changes. 

?? (This needs some way to mark the change to allow contests to reject fixed submissions. ) 

The system will then add QSL data pulled from a conversation logged into itself or an external logbook file. Encryption is again used with the same pgp key. But the conversation is stored as a separate file from the html Digital QSL Card data. This will allow servers to only decrypt and compare a very small XML file for confirmation. 

Topics are added as a clear csv file in the QSL parent directory. Reading from contest or other data provided by the logging program of QOC preference dialog. 
Simple Name=Value csv file
This will then be compressed into a singe file. And sent to a Federated/Distributed Ham Log Book server near to the  hams location.

### Digital QSL layout. 

The actual QSL file will consist of a simple compressed directory file. Named using a ??tbd Unique ID

**QSL-ID-Code/**
>    **QSL-Members/**
This directory consists of a collection of Digital QSL card for all members of a conversation. Each card consists of a Directory Named using the Members Call Sign
>> **Member ID/**
>>**Member Public Key.txt** An open txt file
>>**DQSL Display/**
>>> Directory Encripted using the members privrate key Containing
>>> index.html Simple html file allowing Textual and table elements plus simple images
>>> index.css Simple positioning font and colour data for index.html
>>> data.csv Simple Name=Value csv file providing easy to read data such as 
>>>>Call Sign, Other known IDs, Name Location, And any other data the ham feels needs to be easy to translate/screen read 
>>> Contact.csv Simple Name=Value csv file providing details of the contact. Fields include 
>>>>Member0=TxCallSign, Member(n)=RxCallSign(multiple allowed for nets etc),Mode=(e.g. SSB or FT8),Date=yyyymmdd,Time=24HH:MM-(UTC difference as HH:MM),(other data as expected by user or required by contest/ota rules)
