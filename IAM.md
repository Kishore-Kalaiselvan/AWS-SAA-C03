### What is IAM ?
- IAM - Identity and Access Management is a AWS service Used for Authentication & Authorization
- Root account created by default
- Users are people within your organisation and can be grouped
- Groups only contains users, not other groups
- Users dont have to belong to a group and user can belong to multiple groups

### What is IAM Policy
- Users or groups can be assigned JSON documents called policies
- These policies define the permissions of the Users
- In AWS you apply least privilege principle. (user ku evolo permission thevaiyo antha mattum kudukurathu not giving more than that)

Antha Policy oda structure is :
- 1st version (MANDATORY)
- 2nd id (not mandatory)
- 3rd statement (MANDATORY)
antha statement kulla :
 - statement id (not mandatory)
 - effect
 - principal
 - action 
 - resources 

IAM password: ithula enna paka porom na 
IAM user ku password epdi set panna porom 
initially company user create panumbothu standard password vechu create panni kuduthiruvanga with a condition, user 1st time login panumbothu antha password ah change pannanum
password ku conditions kuda namma customize panikalam, like ethana upper case irukanum ethana lower case irukanum nu elame customize panikalam 

innu 2 enna na :
   i. password expiration (certain period of time la password ah change panite irukanum)
  ii. prevent password re-use (oru time use panna password thirupi use panama pathukanum)

next, MFA
MFA - Multi Factor Authentication 
simple ah solanuna additional layer of protection to the AWS account 
even if password leak aagitalum account can be still protected 
athulaiye neraiya types iruku like google/microsoft authenticator, physical devices um iruku

next little interesting, AWS ah entha entha valiya ellam access panna mudiyum 
main ah 3 
1. AWS console 
2. CLI - Command Line Interface 
3. SDK - Software Development Kit 
 Console na normal ah website la aws login nu poi username + password + MFA kuduthu login panrathu
 CLI na laptop la command prompt la login poanrathu 
 SDK na oru programming language la code eluthi athuvaliya login panrathu 
console valiya login panna username password iruntha pothum 
but CLI and SDK valiya login pannanuna "access key" nu onnu venum antha access key irunthaal matume unala login panna mudiyum 
access key consist of key ID and secret key 
atha yarkitayu share panna kudathu 

next, IAM Roles 
roles na onnu kedaiyathu unoda behalf la sila work ah roles automatic ah pannum 
ana antha roles ku nee permission kudukanum unoda behalf la athu enna enna panalam nu nee tha antha role ku permission set pananu apo tha athu velaiya seiyum 
It is a best practice to use roles 

next the last one : Security Tools 
athula 2 iruku 
1. Credential report (account level) : enna panum na basic oru root account la neraiya IAM users irupanga so avanga status ela therinjuka intha report use aagum.
2. Access advisor report (user level) : ithu enna panumna mela iruka antha report vanthu user pathi therinjukalam password vechirukangala ilaya MFA vechirukangala ilaiya account secure ah iruka password crt ah maathunangalaa nu pakalam 
ana ithu vanthu innu ulla deep ah paakalam like enna enna services epo last ah use pananga enna enna services ku access iruku, atha correct ah use panrangala nu ella pakalam 
avolo simple finished .

