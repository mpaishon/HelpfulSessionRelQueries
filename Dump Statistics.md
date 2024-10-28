# Dump Infrastructure Statistics. 
**Description**: Run this is presentation debugger within the console. This will take a while to run and the console may seem to lock up... This is not abnormal, give it the time to work. To run presentation debugger go here https://developer.bigfix.com/tools/presentation_debugger.html. Assure you evaluate it as HTML. 


```html


<head>
</head>
 <body>

<center>
<h2>BigFix Triage Report</h2>
</center>
<br>
<span><b>Report Generated @ </b> <?Relevance now  ?></span>
<br>



<h3>Deployment stats </h3>
<span><b>Cache Latency Metric: </b><?Relevance (now - (maximum of (last report time of it) of bes computers whose (exist last report time of it))) ?></span>
<br>
<span><b># of Computers:</b> <?Relevance Number of bes computers ?></b></span> 
<br>	
<span><b># of Relays: </b><?Relevance Number of bes computers whose (relay server flag of it) ?></span>
<br>
<span><b>Serial Number of deployment: </b><?Relevance ((site number of bes license) as string) ?></span>
<br>
<span><b>Gather URL </b><?Relevance gather url of bes license ?></span>
<br>
<span><b>Deployment Options </b><?Relevance concatenation ", " of (it as string) of (name of it & "--" & value of it) of bes deployment options?></span>
<br>



<h3>Property activation stats </h3>
<span><b># of Properties</b></span> <?Relevance number of bes properties?> 
<br>
<span><b># of Custom Properties</b></span> <?Relevance number of bes properties whose (custom flag of it)?> 
<br>
<span><b># of Active Properties</b></span> <?Relevance number of properties of bes fixlets whose (analysis flag of it AND exists activation of it AND exists active flags of activations of it)?> 
<br>
<span><b># of Activated Analysis</b></span> <?Relevance number of bes fixlets whose (analysis flag of it AND exists activation of it AND exists active flags of activations of it)?> 
<br>
<span><b># of Property Activations sourced within custom sites:</b> <?Relevance number of (names of it, names of sites of source analyses of it, ids of it, names of issuers of best activations of source analyses of it) of bes properties whose( (custom site flag of source analysis of it ) AND (active flag of best activation of it OR active flag of activation of it) of source analysis of it) ?> </span>
<br>
<span><b># of Property Activations sourced from opsite content:</b> <?Relevance number of (names of it, names of sites of source analyses of it, ids of it, names of issuers of best activations of source analyses of it) of bes properties whose( (operator site flag of source analysis of it ) AND (active flag of best activation of it OR active flag of activation of it) of source analysis of it) ?> </span>
<br>
<span><b># of Property Activations sourced from actionsite content:</b> <?Relevance number of (names of it, names of sites of source analyses of it, ids of it, names of issuers of best activations of source analyses of it) of bes properties whose( (master site flag of source analysis of it) AND (active flag of best activation of it OR active flag of activation of it) of source analysis of it) ?> </span>
<br>
<span><b># of Property Activations sourced from external site content:</b> <?Relevance number of (names of it, names of sites of source analyses of it, ids of it, names of issuers of best activations of source analyses of it) of bes properties whose( (external site flag of site of source analysis of it) AND (active flag of best activation of it OR active flag of activation of it) of source analysis of it) ?> </span>
<br>


<h3>Operator stats </h3>
<span><b># of Master Operators:</b> <?Relevance Number of bes users whose (master flag of it) ?></span> 
<br>	
<span><b># of Non Master Operators:</b> <?Relevance Number of bes users whose (not(master flag of it)) ?></span> 
<br>
<span><b># of Bes Roles:</b> <?Relevance Number of bes roles ?></span> 
<br>
<span><b>Number of operators created within the last 24 hours:</b> <?Relevance number of bes users whose (( exist creation time of it) and ( creation time of it >= (now - 24*hour) )) ?></span>
<br>
<span><b>Number of operators logged in within the last 24 hours:</b> <?Relevance number of bes users whose (( exist last login time of it) and ( last login time of it >= (now - 24 * hour) )) ?></span> 
<br>
<span><b>Number of operators that have not logged in for over 90 days:</b> <?Relevance number of bes users whose ( (exist last login time of it and last login time of it <= (now - 90*day)) and exist last login time of it ) ?></span> 
<br>
<span><b>Number of operators that have not logged in for over 60 days:</b> <?Relevance number of bes users whose ( (exist last login time of it and last login time of it <= (now - 60*day)) and exist last login time of it ) ?></span> 
<br>
<span><b>Number of operators that have not logged in for over 30 days:</b> <?Relevance number of bes users whose ( (exist last login time of it and last login time of it <= (now - 30*day)) and exist last login time of it ) ?></span> 
<br>
<span><b>Number of operators that have never logged in:</b> <?Relevance number of bes users whose ( not (exist last login time of it ))?></span> 
<br>


<h3> Machine check-in stats (including relays and clients) </h3>
<span><b>Latest Computer Report Time timestamp: </b><?Relevance Maximum of (last report time of it) of bes computers ?></span>
<br>
<span><b>Earliest Computer Report Time timestamp: </b><?Relevance Minimum of (last report time of it) of bes computers ?></span>
<br>
<span><b>Number of machines reported within the last 24 hours: </b><?Relevance number of bes computers whose (last report time of it > (now - (24* hour))) ?></span>
<br>
<span><b>Number of machines reported within the last 1 hours: </b><?Relevance number of bes computers whose (last report time of it > (now - (1* hour))) ?>	</span>
<br>
<span><b>Number of machines reported within the last 15 minutes: </b><?Relevance number of bes computers whose (last report time of it > (now - (15 * minute))) ?></span>
<br>






<h3> Action stats </h3>
<span><b># of Actions:</b> <?Relevance Number of bes actions ?></span> 
<br>
<span><b># of Actions by current State:</b> <?Relevance concatenations "; "of ("(" & it & ": " & ( multiplicity of it) as string & ")") of unique values of states of  bes actions whose (exist state of it) ?></span> 
<br>
<span><b>Large multiple action group in open state with greater than 100 component actions: </b><?Relevance number of  bes actions whose  (multiple flag of it and number of member actions of it > 100 and state of it = "Open") ?></span>
<br>
<span><b>Large multiple action group in open state with greater than 250 component actions: </b><?Relevance number of  bes actions whose  (multiple flag of it and number of member actions of it > 250 and state of it = "Open") ?></span>
<br>		
<span><b>Large multiple action group in open state with greater than 500 component actions: </b><?Relevance number of  bes actions whose  (multiple flag of it and number of member actions of it > 500 and state of it = "Open") ?></span>
<br>
<span><b>Open actions targeting method specified: </b><?Relevance concatenations "; "of ("(" & it & ": " & ( multiplicity of it) as string & ")") of unique values of targeting methods of bes actions whose (state of it as lowercase = "open" and exist targeting method of it)?></span>
<br>
<span><b>Number of  actions with multiple flag specified: </b><?Relevance Number of bes actions whose (exist multiple flag of it and multiple flag of it)?></span>
<br>
<span><b>Number of  actions with single flag specified: </b><?Relevance Number of bes actions whose (exist single flag of it and single flag of it)?></span>
<br>
<span><b>Number of open actions associated to content that has since been superseded: </b><?Relevance number of bes actions whose (exist mime field "x-fixlet-superseded" of source fixlet of it and state of it = "Open")?></span>
<br>
<span><b>Number of open actions issued by master operators: </b><?Relevance number of bes actions whose ((exist state whose (it as lowercase = "open") of it) AND (exist issuer whose (master flag of it) of it)) ?></span>
<br>
<span><b>Number of open actions issued by non master operators: </b><?Relevance number of bes actions whose ((exist state whose (it as lowercase = "open") of it) AND (exist issuer whose (NOT master flag of it) of it)) ?></span>
<br>


<h4>Actions by issuer (regardless of state)</h4>
<span><b>Description:</B>This section inllustrates operators with a count of actions issued from that operator regardless of state</span>
<table border="1" width="95%">
<tr>
<td><b>Issuer</b></td>
<td><b>Number of actions</b></td>
</tr>
<?Relevance
concatenation of trs of 
(  
(td "width=600" of ((item 0 of it) as string) & td "width=200" of ( item 1 of it as string) ) 
)
OF
(it, multiplicity of it) of unique values of names of issuers of bes actions whose (exist name of issuer of it)
?>
</table>



<h4>Actions by issuer for open actions</h4>
<span><b>Description:</B>This section inllustrates operators with a count of open actions issued from that operator</span>
<table border="1" width="95%">
<tr>
<td><b>Issuer</b></td>
<td><b>Number of open actions</b></td>
</tr>
<?Relevance
concatenation of trs of 
(  
(td "width=600" of ((item 0 of it) as string) & td "width=200" of ( item 1 of it as string) ) 
)
OF
(it, multiplicity of it) of unique values of names of issuers of bes actions whose (exist name of issuer of it and exist state of it and state of it = "Open")
?>
</table>


<h4>Actions by Date (by status)</h4>
<span><b>Description:</B>This section inllustrates action activity over duration, and the appropriate states.</span>
<table border="1" width="95%">
<tr>
<td><b>Timeframe</b></td>
<td><b>State</b></td>
<td><b># of actions in state</b></td>
</tr>
<?Relevance
concatenation of trs of 
(  
td of ((item 0 of it) as string)
& td of ((item 0 of item 1 of it) as string)
& td of ((item 1 of item 1 of it)  as string)
)
OF
(
( "Actions issued Today",(it,multiplicity of it) of unique values of states of  bes actions whose ( (exist state of it) AND (exist time issued of it) and (time issued of it > (now - (1 * day)))))
;( "Actions issued less than 7 days ago",(it,multiplicity of it) of unique values of states of  bes actions whose ( (exist state of it) AND (exist time issued of it) and (time issued of it > (now - (7 * day)))))
;( "Actions issued less than 15 days ago",(it,multiplicity of it) of unique values of states of  bes actions whose ( (exist state of it) AND (exist time issued of it) and (time issued of it > (now - (15 * day)))))
;( "Actions issued less than 30 days ago",(it,multiplicity of it) of unique values of states of  bes actions whose ( (exist state of it) AND (exist time issued of it) and (time issued of it > (now - (30 * day)))))
;( "Actions issued less than 60 days ago",(it,multiplicity of it) of unique values of states of  bes actions whose ( (exist state of it) AND (exist time issued of it) and (time issued of it > (now - (60 * day)))))
;( "Actions issued less than 90 days ago",(it,multiplicity of it) of unique values of states of  bes actions whose ( (exist state of it) AND (exist time issued of it) and (time issued of it > (now - (90 * day)))))
;( "Actions issued greater than 15 days ago",(it,multiplicity of it) of unique values of states of  bes actions whose ( (exist state of it) AND (exist time issued of it) and (time issued of it < (now - (90 * day)))))
;( "Actions issued without an issue date",(it,multiplicity of it) of unique values of states of  bes actions whose ( (exist state of it) AND (NOT exist time issued of it) ))
;( "All Time Action issue state",(it,multiplicity of it) of unique values of states of  bes actions whose ( (exist state of it) AND (exist time issued of it)))
)
?>
</table>


<h4>Actions by source site</h4>
<span><b>Description:</B>This section inllustrates for fixlets sourced by content, what content site was the content derived from. This also provides the state for the given actions as well.</span>
<table border="1" width="95%">
<tr>
<td><b>Site name</b></td>
<td><b>State</b></td>
<td><b># of actions in state</b></td>
</tr>
<?Relevance
concatenation of trs of 
(  
td of ((item 0 of it) as string)
& td of ((item 1 of it) as string)
& td of ((item 2 of it)  as string)
)
OF
(
 (it, "Open",  (multiplicity of it) as string) of unique values of names of sites of source fixlets whose (exist site of it) of bes actions whose( exist source fixlet of it and state of it = "Open");
 (it, "Stopped",  (multiplicity of it) as string) of unique values of names of sites of source fixlets whose (exist site of it) of bes actions whose( exist source fixlet of it and state of it = "Stopped");
 (it, "Expired",  (multiplicity of it) as string) of unique values of names of sites of source fixlets whose (exist site of it) of bes actions whose( exist source fixlet of it and state of it = "Expired"))
?>
</table>






<h3>Content stats </h3>
<span><b>Total # of bes external sites :</b> <?Relevance Number of bes sites ?></span>
<br>
<span><b>Total # of bes custom sites :</b> <?Relevance Number of bes custom sites ?></span>
<br>
<span><b>Total # of Fixlets :</b> <?Relevance Number of bes fixlets ?></span>
<br>
<span><b>Total # of external site Fixlets :</b> <?Relevance Number of bes fixlets whose (not custom flag of it) ?></span>
<br>
<span><b>Total # of custom Fixlets :</b> <?Relevance Number of bes fixlets whose (custom flag of it)?></span>
<br>
<span><b>Total # of External Site Fixlets:</b> <?Relevance Number of bes fixlets whose ( (NOT (custom site flag of it)) AND (NOT (operator site flag of it))) ?> </span>
<br>
<span><b>Most recent content modification time stamp:</b> <?Relevance maximum of (modification time of it) of bes fixlets whose (  (NOT (custom site flag of it)) AND (NOT (operator site flag of it))  AND exist( modification time of it)) ?></span>
<br>
<span><b>Most recent content creation time stamp:</b> <?Relevance maximum of (creation time of it) of bes fixlets whose ( (NOT (custom site flag of it)) AND (NOT (operator site flag of it))  AND exist( creation time of it)) ?></span>
<br>
<span><b>Most recent x-fixlet-first-propagation time stamp:</b> <?Relevance maximum of (mime field "x-fixlet-first-propagation" of it as time) of bes fixlets whose ((exist (mime field whose (name of it = "x-fixlet-first-propagation" and exist (value whose (exist (it as string as time))of it)) of it))) ?></span>
<br>
<span><b># of Automatic Computer Groups:</b> <?Relevance Number of bes computer groups whose (Automatic flag of it) ?></span>
<br>
<span><b># of Manual Computer Groups:</b> <?Relevance Number of bes computer groups whose (NOT(Automatic flag of it)) ?></span>
<br>



<h4>External sites and versions </h4>
<table border="1" width="95%">
<tr>
<td><b>Display Name</b></td>
<td><b>Site Version</b></td>
<td><b># of Subscribed computers</b></td>
<td><b>Most recent fixlet modification</b></td>
<td><b># of fixlets within the site</b></td>
<td><b>URL</b></td>
</tr>

<?Relevance
concatenation of trs of (
  td of  (display name of it) 
  & td of (version of it as string) 
  & td of (number of subscribed computers of it as string) 
  & td of ((maximum of modification times of fixlets whose (exist modification time of it) of it) as string) 
  & td of  ((number of fixlets whose (not custom flag of it)of it) as string)
  & td of (url of it) 
  ) of unique values of  sites of bes fixlets

  whose  
(
NOT (Custom Flag of it)
AND (NOT (custom site flag of it)) 
AND (NOT (operator site flag of it))  
) 
?>
</table>



<h4>Custom Sites</h4>
<table border="1" width="95%">
<tr>
<td><b>Site Name</b></td>
<td><b># of Subscribed computers</b></td>
<td><b># of fixlets within the site</b></td>
<td><b># of writers to site</b></td>
<td><b># of readers to site</b></td>
<td><b># of owners to site</b></td>
</tr>

<?Relevance
 concatenation of trs of (
  td of  ( name of it) 
  & td of (number of subscribed computers of it as string) 
  & td of  ((number of fixlets whose (custom flag of it)of it) as string)
  & td of (number of writers of it as string) 
  & td of (number of readers of it as string) 
  & td of (number of owners of it as string) 

  ) of unique values of bes custom sites 


?>
</table>



<h4>ICMP Failsafe Settings</h4>
<table border="1" width="95%">
<tr>
<td><b>Value of __RelaySelect_Automatic</b></td>
<td><b>Number of machines</b></td>
</tr>

<?Relevance
(
concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
"__RelaySelect_Automatic = 1",(number of bes computers whose (exist client setting whose ( name of it = "__RelaySelect_Automatic" and value of it as string = "1" ) of it)) as string;
"__RelaySelect_Automatic = 0",(number of bes computers whose (exist client setting whose ( name of it = "__RelaySelect_Automatic" and value of it as string = "0" ) of it)) as string
)
)
?>
</TABLE>



<table border="1" width="95%">
<tr>
<td><b>Value of _BESClient_RelaySelect_MaximumTTLToPing</b></td>
<td><b>Number of machines</b></td>
</tr>
<?Relevance
(concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
("Undefined",((
 number of bes computers whose 
(
   exist client setting whose ( name of it = "__RelaySelect_Automatic" and value of it as string = "1" ) of it
AND 
   NOT(exist client setting whose ( name of it  = (("_BESClient_RelaySelect_MaximumTTLToPing")) and exist value of it ) of it)
) 
) as string))
;
(((it) as string,(multiplicity of it) as string) of unique values of values of client settings whose (name of it  = ("_BESClient_RelaySelect_MaximumTTLToPing" )) of bes computers whose (exist client setting whose ( name of it = "__RelaySelect_Automatic") of it))
)
)
?>
</table>

<table border="1" width="95%">
<tr>
<td><b>Value of _BESClient_RelaySelect_IntervalSeconds</b></td>
<td><b>Number of machines</b></td>
</tr>
<?Relevance
(concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
("Undefined",((
 number of bes computers whose 
(
   exist client setting whose ( name of it = "__RelaySelect_Automatic" and value of it as string = "1" ) of it
AND 
   NOT(exist client setting whose ( name of it  = (("_BESClient_RelaySelect_IntervalSeconds") ) and exist value of it ) of it)
) 
) as string))
;
(((it) as string,(multiplicity of it) as string) of unique values of values of client settings whose (name of it  = ("_BESClient_RelaySelect_IntervalSeconds" )) of bes computers whose (exist client setting whose ( name of it = "__RelaySelect_Automatic") of it))
)
)
?>
</table>


<table border="1" width="95%">
<tr>
<td><b>Value of _BESClient_RelaySelect_MaxRetryIntervalSeconds</b></td>
<td><b>Number of machines</b></td>
</tr>
<?Relevance
(concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
("Undefined",((
 number of bes computers whose 
(
   exist client setting whose ( name of it = "__RelaySelect_Automatic" and value of it as string = "1" ) of it
AND 
   NOT(exist client setting whose ( name of it  = (("_BESClient_RelaySelect_MaxRetryIntervalSeconds") ) and exist value of it ) of it)
) 
) as string))
;
(((it) as string,(multiplicity of it) as string) of unique values of values of client settings whose (name of it  = ("_BESClient_RelaySelect_MaxRetryIntervalSeconds" )) of bes computers whose (exist client setting whose ( name of it = "__RelaySelect_Automatic") of it))
)
)
?>
</table>



<table border="1" width="95%">
<tr>
<td><b>Value of _BESClient_RelaySelect_MinRetryIntervalSeconds</b></td>
<td><b>Number of machines</b></td>
</tr>
<?Relevance
(concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
("Undefined",((
 number of bes computers whose 
(
   exist client setting whose ( name of it = "__RelaySelect_Automatic" and value of it as string = "1" ) of it
AND 
   NOT(exist client setting whose ( name of it  = (("_BESClient_RelaySelect_MinRetryIntervalSeconds")  ) and exist value of it ) of it)
) 
) as string))
;
(((it) as string,(multiplicity of it) as string) of unique values of values of client settings whose (name of it  = ("_BESClient_RelaySelect_MinRetryIntervalSeconds" )) of bes computers whose (exist client setting whose ( name of it = "__RelaySelect_Automatic") of it))
)
)
?>
</table>



<table border="1" width="95%">
<tr>
<td><b>Value of _BESClient_RelaySelect_ResistFailureIntervalSeconds</b></td>
<td><b>Number of machines</b></td>
</tr>
<?Relevance
(concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
("Undefined",((
 number of bes computers whose 
(
   exist client setting whose ( name of it = "__RelaySelect_Automatic" and value of it as string = "1" ) of it
AND 
   NOT(exist client setting whose ( name of it  = (("_BESClient_RelaySelect_ResistFailureIntervalSeconds") ) and exist value of it ) of it)
) 
) as string))
;
(((it) as string,(multiplicity of it) as string) of unique values of values of client settings whose (name of it  = ("_BESClient_RelaySelect_ResistFailureIntervalSeconds" )) of bes computers whose (exist client setting whose ( name of it = "__RelaySelect_Automatic") of it))
)
)
?>
</table>



<h4>Client settings typically of interest</h4>


<table border="1" width="95%">
<tr>
<td><b>Value of _BESClient_Report_MinimumInterval</b></td>
<td><b>Number of machines</b></td>
</tr>
<?Relevance
(concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
("Default",((
 number of bes computers whose 
(
   NOT(exist client setting whose ( name of it as lowercase = (("_BESClient_Report_MinimumInterval")as lowercase) and exist value of it ) of it)
) 
) as string))
;
(((it) as string,(multiplicity of it) as string) of unique values of values of client settings whose (name of it as lowercase = ("_BESClient_Report_MinimumInterval" as lowercase)) of bes computers )
)
)
?>
</table>




<table border="1" width="95%">
<tr>
<td><b>Value of _BESClient_Resource_InterruptSeconds</b></td>
<td><b>Number of machines</b></td>
</tr>
<?Relevance
(concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
("Default",((
 number of bes computers whose 
(
   NOT(exist client setting whose ( name of it as lowercase = (("_BESClient_Resource_InterruptSeconds")as lowercase) and exist value of it ) of it)
) 
) as string))
;
(((it) as string,(multiplicity of it) as string) of unique values of values of client settings whose (name of it as lowercase = ("_BESClient_Resource_InterruptSeconds" as lowercase)) of bes computers )
)
)
?>
</table>


<table border="1" width="95%">
<tr>
<td><b>Value of _BESClient_Comm_CommandPollEnable</b></td>
<td><b>Number of machines</b></td>
</tr>
<?Relevance
(concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
("Default",((
 number of bes computers whose 
(
   NOT(exist client setting whose ( name of it as lowercase = (("_BESClient_Comm_CommandPollEnable")as lowercase) and exist value of it ) of it)
) 
) as string))
;
(((it) as string,(multiplicity of it) as string) of unique values of values of client settings whose (name of it as lowercase = ("_BESClient_Comm_CommandPollEnable" as lowercase)) of bes computers )
)
)
?>
</table>



<table border="1" width="95%">
<tr>
<td><b>Value of _BESClient_Comm_CommandPollIntervalSeconds</b></td>
<td><b>Number of machines</b></td>
</tr>
<?Relevance
(concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
("Default",((
 number of bes computers whose 
(
   NOT(exist client setting whose ( name of it as lowercase = (("_BESClient_Comm_CommandPollIntervalSeconds")as lowercase) and exist value of it ) of it)
) 
) as string))
;
(((it) as string,(multiplicity of it) as string) of unique values of values of client settings whose (name of it as lowercase = ("_BESClient_Comm_CommandPollIntervalSeconds" as lowercase)) of bes computers )
)
)
?>
</table>


<table border="1" width="95%">
<tr>
<td><b>Value of _BESClient_Comm_CommandPollIntervalSeconds</b></td>
<td><b>Number of machines</b></td>
</tr>
<?Relevance
(concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
("Default",((
 number of bes computers whose 
(
   NOT(exist client setting whose ( name of it as lowercase = (("_BESClient_Resource_WorkNormal")as lowercase) and exist value of it ) of it)
) 
) as string))
;
(((it) as string,(multiplicity of it) as string) of unique values of values of client settings whose (name of it as lowercase = ("_BESClient_Resource_WorkNormal" as lowercase)) of bes computers )
))
?>
</table>


<table border="1" width="95%">
<tr>
<td><b>Value of _BESClient_Resource_SleepNormal</b></td>
<td><b>Number of machines</b></td>
</tr>
<?Relevance
(concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
("Default",((
 number of bes computers whose 
(
   NOT(exist client setting whose ( name of it as lowercase = (("_BESClient_Resource_SleepNormal")as lowercase) and exist value of it ) of it)
) 
) as string))
;
(((it) as string,(multiplicity of it) as string) of unique values of values of client settings whose (name of it as lowercase = ("_BESClient_Resource_SleepNormal" as lowercase)) of bes computers )
))
?>
</table>



<table border="1" width="95%">
<tr>
<td><b>Value of _BESClient_Resource_SleepIdle</b></td>
<td><b>Number of machines</b></td>
</tr>
<?Relevance
(concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
("Default",((
 number of bes computers whose 
(
   NOT(exist client setting whose ( name of it as lowercase = (("_BESClient_Resource_SleepIdle")as lowercase) and exist value of it ) of it)
) 
) as string))
;
(((it) as string,(multiplicity of it) as string) of unique values of values of client settings whose (name of it as lowercase = ("_BESClient_Resource_SleepIdle" as lowercase)) of bes computers )
))
?>
</table>



<table border="1" width="95%">
<tr>
<td><b>Value of _BESClient_Resource_WorkIdle</b></td>
<td><b>Number of machines</b></td>
</tr>
<?Relevance
(concatenation of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )of
(
("Default",((
 number of bes computers whose 
(
   NOT(exist client setting whose ( name of it as lowercase = (("_BESClient_Resource_WorkIdle")as lowercase) and exist value of it ) of it)
) 
) as string))
;
(((it) as string,(multiplicity of it) as string) of unique values of values of client settings whose (name of it as lowercase = ("_BESClient_Resource_WorkIdle" as lowercase)) of bes computers )
))

?>
</table>

<h3> Relay stats </h3>
<span><b>Latest relay Report Time timestamp: </b><?Relevance Maximum of (last report time of it) of bes computers whose (relay server flag of it)?></span>
<br>
<span><b>Number of relays reported within the last 24 hours: </b><?Relevance number of bes computers whose (last report time of it > (now - (24* hour)) and relay server flag of it) ?></span>
<br>
<span><b>Number of relays reported within the last 1 hours: </b><?Relevance number of bes computers whose (last report time of it > (now - (1* hour)) and relay server flag of it) ?>	</span>
<br>
<span><b>Number of relays reported within the last 15 minutes: </b><?Relevance number of bes computers whose (last report time of it > (now - (15 * minute)) and relay server flag of it) ?></span>
<br>
<span><b>Number of relays that have not reported within the last 1 hour: </b><?Relevance number of bes computers whose (last report time of it < (now - (60 * minute)) and relay server flag of it) ?></span>
<br>
<span><b>Number of relays that have not reported within the last 1 day : </b><?Relevance number of bes computers whose (last report time of it < (now - (1440 * minute)) and relay server flag of it) ?></span>
<br>
<span><b>Number of relays that have not reported within the last 1 day : </b><?Relevance number of bes computers whose (last report time of it < (now - (10080 * minute)) and relay server flag of it) ?></span>
<br>
<span><b>Number of Relays with over 1000 Clients: </b><?Relevance number of (item 0 of it) of ((it, multiplicity of it) of unique values of (relay servers of it) of bes computers whose (exist relay server of it)) whose (item 1 of it > 1000)?></span>
<br>		


<h4>Relay Server Aggregation Statistics (Total Child Count) </h4>
<table border="1" width="95%">
<tr>
<td><b>Relay Name</b></td>
<td><b>Number of machines</b></td>
</tr>

<?Relevance
concatenations of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )
of 
((it, multiplicity of it) of unique values of (relay server of it) of bes computers whose (exist relay server of it))
?>

</table>
<br>

<h4>Relay Server Aggregation Statistics (Client Child Count) </h4>
<table border="1" width="95%">
<tr>
<td><b>Relay Name</b></td>
<td><b>Number of machines</b></td>
</tr>

<?Relevance
concatenations of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )
of 
((it, multiplicity of it) of unique values of (relay server of it) of bes computers whose (exist relay server of it AND not relay server flag of it))
?>
</table>
<br>

<h4>Relay Server Aggregation Statistics (Relay Child Count) </h4>
<table border="1" width="95%">
<tr>
<td><b>Relay Name</b></td>
<td><b>Number of machines</b></td>
</tr>

<?Relevance
concatenations of trs of 
(td "width=600" of (item 0 of it) & td "width=200" of ( item 1 of it as string) )
of 
((it, multiplicity of it) of unique values of (relay server of it) of bes computers whose (exist relay server of it AND relay server flag of it))
?>
</table>
<br>


<h4>Relay ActionSite version  (based upon BES Health Checks::Actionsite Version bes property )</h4>
<table border="1" width="95%">
<tr>
<td><b>ActionSite Version</b></td>
<td><b>Name</b></td>
<td><b>Last Report time</b></td>
</tr>
<?Relevance
(
concatenation of trs of 
(
 td of ((item 0 of item 1 of it) as string) of it
 & td of ((item 0 of item 1 of item 1 of it) as string) of it
 & td of ((item 1 of item 1 of item 1 of it) as string) of it
)
of
(
maximum of unique values of ((values of it) as integer) of results of (bes properties whose (name of it = "BES Health Checks::Actionsite Version" )),
(value of it,(name of it,last report time of it) of computer of it) of results of(bes properties whose(name of it="BES Health Checks::Actionsite Version" ))
)
whose (((item 0 of item 1 of it) as integer) = (item 0 of it) as integer)
)
?>
</table>



<h3>Core servers stats</h3>
<span><b>Core servers CPU Stats</b><?Relevance concatenation ", " of values of results from (bes properties "CPU") whose (exists value of it) of computers of results whose (exists value of it and value of it = "BES Root Server" or value of it = "Main BES Server") of bes properties "Relay" whose (reserved flag of it) ?> </span>
<br>
<span><b>Core servers RAM Stats</b><?Relevance concatenation ", " of values of results from (bes properties "RAM") whose (exists value of it) of computers of results whose (exists value of it and value of it = "BES Root Server" or value of it = "Main BES Server") of bes properties "Relay" whose (reserved flag of it) ?> </span>
<br>
<span><b>Core servers OS Stats</b><?Relevance concatenation ", " of values of results from (bes properties "OS") whose (exists value of it) of computers of results whose (exists value of it and value of it = "BES Root Server" or value of it = "Main BES Server") of bes properties "Relay" whose (reserved flag of it) ?></span>
<br>
<span><b>Core servers HW Stats</b><?Relevance Table "border=1" of concatenation of trs of tds of unique values of (it as trimmed string) of values of (results (properties of bes fixlets whose (analysis flag of it = TRUE AND name of it as lowercase contains "hardware information"), it) whose (exists value of it)) of bes computers whose (exists value of result (bes properties "Relay" whose (reserved flag of it),it) and (value of result (bes properties "Relay" whose (reserved flag of it),it) = "BES Root Server" or value of result (bes properties "Relay" whose (reserved flag of it),it) = "Main BES Server"))?></span>


<h4>All client settings of core servers</h4>
<table border="1" width="95%">
<tr>
<td><b>Setting Name</b></td>
<td><b>Setting Value</b></td>
<td><b>Name of Core server</b></td>
</tr>
<?Relevance
 concatenations of trs of (
td of item 0 of item 0 of it
& td of item 1 of item 0 of it
& td of item 1 of it
)
of
(((name of it|"no val"), (value of it|"no val")) of client settings of it, name of it) of bes computers whose (root server flag of it)
?>
</table>

<h3>Application component versions</h3>

<h4>Version of Clients</h4>
<table border="1" width="95%">
<tr>
<td><b>Client Version</b></td>
<td><b>Number of Clients</b></td>
</tr>
<?Relevance
concatenation of trs of (td "width=600" of it & td "width=600" of (multiplicity of it as string)) of unique values of values of results whose (not error flag of it and exists value of it) of bes property whose (name of it = "BES Client Version" and name of site of source analysis of it = "BES Support")
?>
</table>

<h4>Version of Consoles</h4>
<table border="1" width="95%">
<tr>
<td><b>Console Version</b></td>
<td><b>Number on version</b></td>
</tr>
<?Relevance
concatenation of trs of (td "width=600" of it & td "width=600" of (multiplicity of it as string)) of unique values of values whose (it contains ".") of results whose (not error flag of it and exists value of it) of bes property whose (name of it = "BES Console Version" and name of site of source analysis of it = "BES Support")
?>
</table>

<h4>Version of API</h4>
<table border="1" width="95%">
<tr>
<td><b>API Version</b></td>
<td><b>Number on version</b></td>
</tr>
<?Relevance
concatenation of trs of (td "width=600" of it & td "width=600" of (multiplicity of it as string)) of unique values of values whose (it contains ".") of results whose (not error flag of it and exists value of it) of bes property whose (name of it = "BES API Version" and name of site of source analysis of it = "BES Support")
?>
</table>


<h4>Version of Server</h4>
<table border="1" width="95%">
<tr>
<td><b>Server Version</b></td>
<td><b>Number on version</b></td>
</tr>
<?Relevance
concatenation of trs of (td "width=600" of it & td "width=600" of (multiplicity of it as string))  of unique values of values whose (it contains ".") of results whose (not error flag of it and exists value of it) of bes property whose (name of it = "BES Server Version" and name of site of source analysis of it = "BES Support")
?>
</table>



<h4>Custom BES Properties with frequent evaluations (sub 5 minutes)</h4>
<table border="1" width="95%">
<tr>
<td><b>Name of property</b></td>
<td><b>Source Analysis site</b></td>
<td><b>BES Property ID</b></td>
<td><b>Names of issuers</b></td>
<td><b>Evaluation Interval</b></td>
</tr>

<?Relevance
 concatenations of trs of
(
td of (item 0 of it)
& td of ((item 1 of it) as string)
& td of ((item 2 of it) as string)
& td of ((item 3 of it) as string)
& td of ((item 4 of it) as string)
)
of
(
(names of it, names of sites of source analyses of it, ids of it, names of issuers of best activations of source analyses of it, evaluation period of it) of bes properties whose(evaluation period of it <= 5*minute AND (custom site flag of source analysis of it OR operator site flag of source analysis of it OR master site flag of source analysis of it) AND (active flag of best activation of it OR active flag of activation of it) of source analysis of it)
)
?>
</table>

 </body>
```