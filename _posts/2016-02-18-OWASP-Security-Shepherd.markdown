---
title:  "OWASP Security-Shepherd Documentation"
date:   2016-02-18 15:04:23
categories: [OWASP Security-Shepherd VBox training]
tags: [OWASP Security-Shepherd VBox training]
---
The OWASP Security Shepherd project is a web and mobile application security training platform. Security Shepherd has been designed to foster and improve security awareness among a varied skill-set demographic. The aim of this project is to take AppSec novices or experienced engineers and sharpen their penetration testing skillset to security expert status.

<html>
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="chrome=1">
    <title></title>
  </head>
  
  <body>
    <div class="wrapper">
      <header>
      <section>
      <hr>
<h2>
<a id="field-training" class="anchor" href="#field-training" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>Field Training</h2>

<h3>
<a id="1insecure-direct-object-references" class="anchor" href="#1insecure-direct-object-references" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*1.Insecure Direct Object References</h3>

<p>First Challenge is "Insecure Direct Object Reference" The Key for this level is stored on Administrator Profile.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139442/a01f94a0-d652-11e5-81f2-8d08cc5abe79.png" alt="1"></p>

<p>We enter the "Refresh Your Profile Button" and Capture the Request using Burp Proxy</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139441/a01c72d4-d652-11e5-80e1-f957405440c3.png" alt="2"></p>

<p>From the Captured request we found that "username = guest"</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139438/9fc434a2-d652-11e5-8c94-fc3010746cff.png" alt="3"></p>

<p>We Changed the user name from "guest" to "admin" and forward the request to the server.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139439/9fc7a7ae-d652-11e5-93fe-a616a1d4c23e.png" alt="4"></p>

<p>and the Server Response with the Result Key</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139440/9fc87990-d652-11e5-81d1-522bf3e15ce3.png" alt="5"></p>

<h3>
<a id="2poor-data-validation" class="anchor" href="#2poor-data-validation" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*2.Poor Data Validation</h3>

<p>Second challenge is "Poor Data Validation", We can get the result key by entering " Negative Number"</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139519/041636d0-d653-11e5-8784-36e9dec606d2.png" alt="1"></p>

<p>Checked whether we can enter the Negative value in the form itself, however the system shows the error message "*An error Occurred: Number Must be Greater that 0 *"</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139522/041a545e-d653-11e5-8641-69cb5e736cc7.png" alt="2"></p>

<p>So we enter the positive value and can tried to change the value using BurpSuite proxy</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139520/04170880-d653-11e5-82ab-a5a040ae1a8b.png" alt="3"></p>

<p>We enter the positive value of "35" and captured that request</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139525/041dcdfa-d653-11e5-84ae-cd38bdad83e2.png" alt="4"></p>

<p>Changed the Value "userdata=35" to "userdata=-35" and forward the request to the server</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139523/041b4878-d653-11e5-84e4-233a89390a36.png" alt="5"></p>

<p>And we got the Result Key</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139521/04176cbc-d653-11e5-9f82-9ecdc7241c99.png" alt="6"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139526/043ac82e-d653-11e5-8ffc-72c8d06dc381.png" alt="7"></p>

<h3>
<a id="3security-misconfiguration" class="anchor" href="#3security-misconfiguration" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*3.Security Misconfiguration</h3>

<p>Third Challenge is Simple We can get the credentials by entering default admin creadentials "Username: admin and Password:passsword"</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139694/cf380a14-d653-11e5-8a17-ee95e40ec239.png" alt="1"></p>

<p>And we got the Result Key for Challenge 3</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139696/cf40caa0-d653-11e5-80c0-c614f4311950.png" alt="2"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139695/cf3f696c-d653-11e5-8e5d-2b6e1a5feb7c.png" alt="3"></p>

<h3>
<a id="4broken-session-management" class="anchor" href="#4broken-session-management" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*4.Broken Session Management</h3>

<p>In this challenge we have to make the server to believe that we have already completed this challenege.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139736/07af2aa8-d654-11e5-82f9-4480e08d7156.png" alt="1"></p>

<p>So we press the Complete this lesson submit button and capture the request using Burpsuite.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139738/07b1f81e-d654-11e5-8b4f-10e5f515d4d3.png" alt="2"></p>

<p>Change the "lessonComplete=lessonNotComplete" to "lessonComplete" and forward the request</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139739/07b26042-d654-11e5-8453-7e64ce5808dc.png" alt="3"></p>

<p>System believes we completed this challenge and responded with the result key</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139737/07b00388-d654-11e5-9119-f6b6d84716ac.png" alt="4"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139740/07b2d022-d654-11e5-86dc-2d9083ded6b7.png" alt="5"></p>

<h3>
<a id="5failure-to-restrict-url-access" class="anchor" href="#5failure-to-restrict-url-access" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*5.Failure to Restrict URL Access</h3>

<p>In this Challenge we have to access the link, only administrator to have access to that link.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139823/64a08f9a-d654-11e5-843c-a34fecf33caa.png" alt="1"></p>

<p>Go through the source using "Inspect elements" or use tools like firebug</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139821/64a0052a-d654-11e5-8adc-cb773fc2d9e1.png" alt="2"></p>

<p>so we delete the none, therefore we can view the administrator result page link</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139824/64a1afec-d654-11e5-8601-04384bf8abe3.png" alt="3"></p>

<p>And we got the result key for this challenge by clicking the link.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139822/64a08176-d654-11e5-8226-6e78f7076787.png" alt="4"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139825/64a33d4e-d654-11e5-9f2b-9b5ed09f4021.png" alt="5"></p>

<h3>
<a id="6cross-site-scripting" class="anchor" href="#6cross-site-scripting" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*6.Cross Site Scripting</h3>

<p>This challenge is Simple Cross Site Scripting (XSS)</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139861/a0aa1e20-d654-11e5-8c73-c1f0c0eb33d5.png" alt="1"></p>

<p>We enter the Basic Script ""</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139864/a0b0380a-d654-11e5-96e3-c87d31d9487d.png" alt="2"></p>

<p>and we got the pop up, so this page is vulnerable to XSS</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139865/a0b6c6de-d654-11e5-99a9-5770cebd5894.png" alt="3"></p>

<p>and we got the *result key *for this challenge</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139863/a0ae3064-d654-11e5-8af1-f1503375e356.png" alt="4"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139862/a0ab56f0-d654-11e5-80c9-efa687b6c088.png" alt="5"></p>

<h3>
<a id="7cross-site-scripting-1" class="anchor" href="#7cross-site-scripting-1" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*7.Cross Site Scripting 1</h3>

<p>This Challenge is another Cross Site Scripting (XSS)</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139909/ffc20fbc-d654-11e5-832b-b9408a8a405c.png" alt="1"></p>

<p>By going through the Source, we found that this page has iframe..</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139907/ffc11ad0-d654-11e5-840b-b9087b96a322.png" alt="2"></p>

<p>So we tried the XSS by including the script into the iframe ""</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139906/ffc06522-d654-11e5-9c02-eadd83e149d9.png" alt="3"></p>

<p>and we got the pop up, so this page is vulnerable to "XSS"</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139910/ffc45cb8-d654-11e5-9417-7cbf8ea63a65.png" alt="4"></p>

<p>we got the result key as well.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139908/ffc177a0-d654-11e5-81ec-c4ace19a7e92.png" alt="5"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139911/ffc48814-d654-11e5-809f-e4fcd69ab200.png" alt="6"></p>

<h2>
<a id="private" class="anchor" href="#private" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>Private</h2>

<h3>
<a id="1insecure-data-storage" class="anchor" href="#1insecure-data-storage" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*1.Insecure Data Storage</h3>

<p>First Challenge in Private is Android Challenge, You have to access the database to get the user credentials and admin password is the key</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139970/58fcd1d4-d655-11e5-9827-fcad5dfbabc2.png" alt="1"></p>

<p>All challenge directories and files are available in data/data</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139969/58fc30d0-d655-11e5-9590-a0149eabb381.png" alt="2"></p>

<p>first challenge is insecure data so access the com.mobshep.insecuredata directory</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139967/58f98268-d655-11e5-9315-493680f7f2bd.png" alt="3"></p>

<p>passwords are available under "com.mobshep.insecuredata/databases" directory and Members file can be access using cat command and password is Battery777</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139968/58f9f586-d655-11e5-8d18-2ff1d89f9685.png" alt="4"></p>

<p>password is Battery777</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139971/58feed5c-d655-11e5-96cc-89ff0f211f61.png" alt="5"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13139972/5900278a-d655-11e5-8f74-797b91a101a7.png" alt="6"></p>

<h3>
<a id="2insecure-cryptographic-storage" class="anchor" href="#2insecure-cryptographic-storage" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*2.Insecure Cryptographic Storage</h3>

<p>This challenge is cryptograpic challenge, however the result key is encoded using "base64"</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140113/280a479a-d656-11e5-94c9-91de386933b9.png" alt="1"></p>

<p>I have decoded using "Hackbar" addon</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140114/280cabf2-d656-11e5-8399-aa40893a0556.png" alt="2"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140115/280d10ec-d656-11e5-9287-86e47af79d84.png" alt="3"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140116/280e3544-d656-11e5-8829-c83c6164f1ab.png" alt="4"></p>

<h3>
<a id="3sql-injection" class="anchor" href="#3sql-injection" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*3.SQL Injection</h3>

<p>This one is SQL Injection Challenge</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140152/50bce0e4-d656-11e5-8854-7f84034854c9.png" alt="1"></p>

<p>Its a simple SQL injection, you can beat it using 'or'1'='1 command. Result key available in the db.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140150/50b8c04a-d656-11e5-8fbf-07c9d897199e.png" alt="2"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140151/50bbdfdc-d656-11e5-9841-37f6415223cb.png" alt="3"></p>

<h3>
<a id="4insecure-cryptographic-storage-challenge1" class="anchor" href="#4insecure-cryptographic-storage-challenge1" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*4.Insecure Cryptographic Storage Challenge1</h3>

<p>Another Cryptographic challenge, this time result key is encrypted using *Roman Cipher(Ceaser Cipher) *</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140692/95a3253a-d659-11e5-9bb9-a67fd837a67f.png" alt="1"></p>

<p>Wrote a simple python script to brute force the Key.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140693/95a45e28-d659-11e5-95c8-5296db2ec126.png" alt="2"></p>

<p>Shift Key is 21 and got the Result Key as well</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140695/95a8300c-d659-11e5-9627-c7ab99cd441e.png" alt="4"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140694/95a750e2-d659-11e5-8270-35fe812f5ecb.png" alt="5"></p>

<h3>
<a id="5insecure-direct-object-reference-challenge-1" class="anchor" href="#5insecure-direct-object-reference-challenge-1" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*5.Insecure Direct Object Reference Challenge 1</h3>

<p>In this challenge you have to access the user who is not listed in the drop down list</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140857/7731fc10-d65a-11e5-9f31-9d0ca1fb4cd8.png" alt="1"></p>

<p>By accessing source could identify ID of users (1,3,5,7,9)</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140856/77311700-d65a-11e5-8693-e89248d3e672.png" alt="2"></p>

<p>SO select the last user and send the request through Burpsuite</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140859/7734e1fa-d65a-11e5-97ce-ef122d7b05b6.png" alt="3"></p>

<p>UserID is 9</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140858/7733b3d4-d65a-11e5-809c-32d77c4836b7.png" alt="4"></p>

<p>Changed the ID from 9 to 11 (which could be next number, you can also brute force the ID using Burp Intruder)</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140860/7735c462-d65a-11e5-8626-e58b2e2f1568.png" alt="5"></p>

<p>and the server respond with the result key</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140855/772f9b96-d65a-11e5-9936-161238c30c80.png" alt="6"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140861/77560ac4-d65a-11e5-8c1f-48f967a74339.png" alt="7"></p>

<h3>
<a id="6poor-data-validation-1" class="anchor" href="#6poor-data-validation-1" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*6.Poor Data Validation 1</h3>

<p>This is data validation challenge, you have to buy free trolls</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140900/b3ec4eee-d65a-11e5-8523-8ea45688283f.png" alt="1"></p>

<p>select 1 Troll and -100 on the meme which $30, therefore your total will be $0 and you will get the Result Key</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140901/b3ecbe1a-d65a-11e5-8883-23855dac7f5d.png" alt="2"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140902/b3efab52-d65a-11e5-9d4e-50ce74d4c1a3.png" alt="3"></p>

<h3>
<a id="7sql-injection-1" class="anchor" href="#7sql-injection-1" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*7.SQL Injection 1</h3>

<p>Another SQL Injection Challenge</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140954/ecb6b2f0-d65a-11e5-9c59-6d2f504f6c1e.png" alt="1"></p>

<p>First test the *'OR'1'='1 *which is not working</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140959/ecbc9350-d65a-11e5-8d5e-077090b19ed7.png" alt="2"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140955/ecb81974-d65a-11e5-8158-06f9da631966.png" alt="3"></p>

<p>From the hint found SQL Query start with "</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140957/ecbc2f32-d65a-11e5-8745-e46019cf0eda.png" alt="4"></p>

<p>So we tried SQL injection with double colon "OR"1"="1 and got the Key</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140958/ecbc4ea4-d65a-11e5-9069-d053283c5d65.png" alt="5"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13140956/ecbad20e-d65a-11e5-8aca-e2d8fb599b25.png" alt="6"></p>

<h3>
<a id="8session-management-challenge-1" class="anchor" href="#8session-management-challenge-1" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*8.Session Management Challenge 1</h3>

<p>Another Session Management Challenge only administrator has access to the application</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141140/b9b534b6-d65b-11e5-8624-6bc919893c71.png" alt="1"></p>

<p>Press the administrator only Submit button and capture the request using Burpsuite. and you can see the Check-sum value</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141143/b9b72410-d65b-11e5-8e52-3c35d1ec5c7e.png" alt="2"></p>

<p>That checksum value is encoded with base64, once you decode it you can see the value "userRole=user"</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141141/b9b5aa54-d65b-11e5-94cb-99832421de83.png" alt="3"></p>

<p>Change the "userRole=user" to "userRole=administrator"</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141142/b9b6ea04-d65b-11e5-8db5-4b4ced02d529.png" alt="4"></p>

<p>Encode "userRole=administrator" using base64</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141144/b9b802ae-d65b-11e5-82cc-e125904ddbb3.png" alt="5"></p>

<p>Change the checksum value in Burpsuite with base64 new encoded value and forward the request to server</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141145/b9b91d24-d65b-11e5-8345-01abc38cf944.png" alt="6"></p>

<p>Server will respond with the result key</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141146/b9ddf504-d65b-11e5-9c48-705344bbe96e.png" alt="7"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141147/b9df0462-d65b-11e5-9d65-9b03fc8985de.png" alt="8"></p>

<h3>
<a id="9failure-to-restrict-url-access" class="anchor" href="#9failure-to-restrict-url-access" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*9.Failure to Restrict URL Access</h3>

<p>Failure to Restrict URL Access Challenge.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141211/1d6be388-d65c-11e5-919d-f782309df78c.png" alt="1"></p>

<p>Press the "Get server Status" Button and capture the request using Burpsuite</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141209/1d6a3e2a-d65c-11e5-9440-a5b99b409770.png" alt="2"></p>

<p>If you go through the source, you will find out the JavaScript code with two form urls one for "leform" and other one is "leadminform"</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141210/1d6b3be0-d65c-11e5-9b82-e7c1330fe9e9.png" alt="3"></p>

<p>You can view that from the Burpsuite captured request client forwarding the normal "leform" url</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141212/1d6d8eea-d65c-11e5-8fd1-732bfb432a0e.png" alt="4"></p>

<p>Change that url with "leadminform" url and forward the request to server</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141247/4298eb1a-d65c-11e5-9316-172d79eb1334.png" alt="5"></p>

<p>Server will respond with the key</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141213/1d6f39fc-d65c-11e5-9fdc-db355f58e336.png" alt="6"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141215/1d931df4-d65c-11e5-84fd-f202844725fe.png" alt="7"></p>

<h3>
<a id="10-unintended-data-leakage" class="anchor" href="#10-unintended-data-leakage" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*10. Unintended Data Leakage</h3>

<p>Another Android Challenge, Here You have to access the logs to find the result ey</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141307/ac13e13a-d65c-11e5-933d-c717e1bb1fe7.png" alt="1"></p>

<p>If you cd the /data/data you can view the udataleakage directory</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141309/ac1a835a-d65c-11e5-8781-eb4604147353.png" alt="2"></p>

<p>inside the directory you can see three files, under the files folder the log file is saved. once you cat the file you can view the key</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141310/ac1bb202-d65c-11e5-8a42-d219dc43ce97.png" alt="3"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141311/ac1c85f6-d65c-11e5-82f5-9a8a33630ca3.png" alt="4"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141308/ac182696-d65c-11e5-926b-05ca37762a8e.png" alt="5"></p>

<h3>
<a id="11cross-site-request-forgery" class="anchor" href="#11cross-site-request-forgery" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*11.Cross Site Request Forgery</h3>

<p>Cross site request forgery challenge</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141362/f31a984e-d65c-11e5-98cb-00b58d2bb8fa.png" alt="1"></p>

<p>You have to send the url with the temp userid to administrator</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141365/f35eab2e-d65c-11e5-83bf-84de88408638.png" alt="2"></p>

<p>server will repsond with the key</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141361/f3163e16-d65c-11e5-90a0-9d36f794a896.png" alt="3"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141363/f31beeec-d65c-11e5-8ccd-01b4545e0692.png" alt="4"></p>

<h3>
<a id="12content-provider-leakage" class="anchor" href="#12content-provider-leakage" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*12.Content Provider Leakage</h3>

<p>Android Challenge, Content Providers are intended to be accessed by other applications, however with the Android Debug Bridge, they can be accessed by anyone with access to a device.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141407/2ecef93e-d65d-11e5-9d62-8724fb0741f3.png" alt="1"></p>

<p>Used "adb shell content query --uri content://com.somewhere.hidden.SecretProvider/data" to get the result key</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141408/2ed2c3ac-d65d-11e5-8e7b-e43581fba7e4.png" alt="2"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141409/2ed4ba4a-d65d-11e5-8b11-0307ae1ff880.png" alt="3"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141410/2ed4ed58-d65d-11e5-8e8a-89aa90818d56.png" alt="4"></p>

<h2>
<a id="corporal" class="anchor" href="#corporal" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>Corporal</h2>

<h3>
<a id="1-unvalidated-redirects-and-forwards" class="anchor" href="#1-unvalidated-redirects-and-forwards" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*1. Unvalidated Redirects and Forwards</h3>

<p>This lesson s CSRF, To exploit you have to include the your intended link to the normal link. This link sent to mar this lesson as completed</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141530/d0bed264-d65d-11e5-8be3-3535266ec879.png" alt="1"></p>

<p>Server will reply with the result key</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141531/d0bf11ac-d65d-11e5-8bcb-38673b97d7f7.png" alt="2"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141532/d0c1dcca-d65d-11e5-95a4-51c543d30392.png" alt="3"></p>

<h3>
<a id="2-client-side-injection" class="anchor" href="#2-client-side-injection" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*2. Client Side Injection</h3>

<p>In this challenge we have to exploit the SQL injection flow on the Android</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141606/3e75a152-d65e-11e5-802f-107f2c916c6c.png" alt="1"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141605/3e742606-d65e-11e5-926a-6ca3da1b7466.png" alt="2"></p>

<p>We have included Admin'OR'user='user command to inject server sad legged in.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141607/3e7dba0e-d65e-11e5-8925-f8d041d7bf7e.png" alt="3"></p>

<p>And gave the key for this for challenge</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141608/3e7f2312-d65e-11e5-81ea-c05b75d6603a.png" alt="4"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141609/3e878606-d65e-11e5-8fa6-53629deb3423.png" alt="5"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141610/3e88757a-d65e-11e5-8947-4192478915de.png" alt="6"></p>

<h3>
<a id="3-sql-injection-2" class="anchor" href="#3-sql-injection-2" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*3. SQL Injection 2</h3>

<p>Another SQL injection Challenge..</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141699/ad91d63c-d65e-11e5-9a90-9b4161dc277a.png" alt="1"></p>

<p>Inject the flow using 'or'1'!='<a href="mailto:shan@yahoo.com">shan@yahoo.com</a> and db gave us the Key..</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141697/ad6638b0-d65e-11e5-9c6d-e7cec642e815.png" alt="2"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141698/ad676032-d65e-11e5-9dd1-951bfed3eb81.png" alt="3"></p>

<h3>
<a id="4-poor-authentication" class="anchor" href="#4-poor-authentication" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*4. Poor Authentication</h3>

<p>This is authentication challenge in the Android</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141863/96b489fe-d65f-11e5-81cc-061d401398d8.png" alt="1"></p>

<p>First You have to open the "Poor Authentication" App</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141862/96b3418e-d65f-11e5-9613-b720fdb9fd30.png" alt="2"></p>

<p>Next screen you have to enter username and password since we do not now the password go for** reset function.**</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141864/96b4ab1e-d65f-11e5-9584-8e8ef8160a9f.png" alt="3"></p>

<p>Next Screen Reset screen you have to enter the answers for some security questions.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141865/96b59628-d65f-11e5-9d4e-3d244223f71d.png" alt="4"></p>

<p>Since we do not know the answers, we access the "com.mobshep.poorauthentication/files" inside directory *logs files *are available (the App is leaking logs of what the user has typed during previous uses of the App. This information will provide you with the data you need to reset the password and get the key.)</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141867/96b8e71a-d65f-11e5-9e95-6cd582bba9e4.png" alt="5"></p>

<p>From That logs you can get the answers for security questions. "Favorite Food: Chicken &amp; Mother's Maiden Name : Meade" Once you enter the correct answers system will give you the temp password</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141866/96b6bf08-d65f-11e5-96f7-74a26a0fd26a.png" alt="6"></p>

<p>You can find the username from the log files and with the temp password you can Login.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141868/96df8672-d65f-11e5-963e-95c94187f4a6.png" alt="7"></p>

<p>And you can get the result key.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141869/96dfd154-d65f-11e5-9f8a-62b0430197ca.png" alt="8"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141870/96e01b00-d65f-11e5-823e-3a3365269932.png" alt="9"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141871/96e2bdb0-d65f-11e5-9104-370e0865f08a.png" alt="10"></p>

<h3>
<a id="5-broken-crypto" class="anchor" href="#5-broken-crypto" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>*5. Broken Crypto</h3>

<p>This is Crypto challenge is Android..</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141996/3bd3f262-d660-11e5-9072-4af83cfe314f.png" alt="1"></p>

<p>First you have to access the Broken Crypto app.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141995/3bcee16e-d660-11e5-89e0-72a4123c4d6e.png" alt="2"></p>

<p>You will get some encrypted text.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141997/3bd4a1ee-d660-11e5-8bed-2c0a1094312f.png" alt="3"></p>

<p>But they used HEX encode to encrypt these text. And last text contains the key.</p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13142000/3bd5d046-d660-11e5-9067-115469b20900.png" alt="4"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141999/3bd55c9c-d660-11e5-86d2-e695a7542bf0.png" alt="5"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13141998/3bd55242-d660-11e5-8692-b3a5b608cb71.png" alt="6"></p>

<p><img src="https://cloud.githubusercontent.com/assets/17286516/13142001/3bf648bc-d660-11e5-918d-ad19dbe9d99d.png" alt="7"></p>

<p>And that completes the broken crypto...</p>


	</section>
	<hr>
	<hr>
    	</div>
    	<!--[if !IE]><script>fixScale(document);</script><![endif]-->
  </body>
</html>
