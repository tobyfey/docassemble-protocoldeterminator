The Protocol Determinator makes it easier for advocates to use data to determine a person's legal needs, and refer to available protocols or otherwise provide specific legal information.

Civil common law as best, most elegant solution.

Our system is failing 

Open types of organization, with open tools for as many people as possible to participate, can provide the open, uniform law.

The Protocol Determinator demonstrates both how we can = provide the best assistance we can to people who need help now while building a better system in the future.

## Gathering Data from Pika and Elsewhere

The Protocol Determinator can be opened in Pika, and pull data from any of the tabs.  The data that is pulled from Pika can be double-checked.

<details>
	<summary>Software issues</summary>
	
###### Software issues
	1. Get data from related parties to the case
	   * link to issues
	2. Add in explanation about 1 and 0 as True and False
	   * link to issues
</details>

<details>
	<summary>Features Requests</summary>
	
###### Features Requests
	1. Pull in data from other sources
	   2. Court dockets
	   3. Property lists
	1. Add tab for protocol determinator
	   
</details>

<details>
	<summary>How it works in docassemble</summary>
	
<br>	
docassemble uses a javascript function to put data from Pika into the fields of a docassemble interview.  Hitting the button at the bottom of the screen brings the data into the docassemble interview.

    ---
    question: Pika Field import
    fields:
      - Address: address
        required: false
      - Case Zip Code: case_zip_code
        required: false
      - Case County: countyAC
        required: false
      - Date Intake Completed: date_intake_completed
        required: false
        datatype: date
      - Hearing Date: hearing_date
        required: false
      - Client Age: client_age
        required: false
        datatype: integer
      - Domestic Violence: domestic_violence
        required: false
      - Sexual Assault: sexual_assault
        required: false
      - Stalking: stalking
        required: false
      - Opposing Party: opposing_party
        required: false
      - Calculated Poverty Rate from Assets Screen: calc_poverty
        required: false
        datatype: number
      - Adjusted Poverty Rate from Liabilities Screen: adj_poverty
        required: false
        datatype: number
      - Minor Children: minor_children
        required: false
        datatype: integer
      - Is applicant receiving any public benefits?: public_benefits
        required: false
      - Problem Code: problem_code
        required: false
      - Special Problem Code: special_problem_code
        required: false
      - Case Number: number
        required: false
    continue button field: pikagathered
    script: |
      <script>
      // address
      document.getElementById('YWRkcmVzcw').value = pika_js["client_address"];
      // Client age
      document.getElementById('Y2xpZW50X2FnZQ').value = pika_js["client_age"];
      // Hearing Date
      document.getElementById('aGVhcmluZ19kYXRl').value = pika_js["date_hearing"];
      // Number
      document.getElementById('bnVtYmVy').value = pika_js["number"];
      // Case County
      document.getElementById('Y291bnR5QUM').value = pika_js["county"];
      // Domestic Violence
      document.getElementById('ZG9tZXN0aWNfdmlvbGVuY2U').value = pika_js["dom_abuse"];
      // Sexual Assault
      document.getElementById('c2V4dWFsX2Fzc2F1bHQ').value = pika_js["sex_assault"];
      // Stalking
      document.getElementById('c3RhbGtpbmc').value = pika_js["stalking"];
      // Date Intake Completed
      document.getElementById('ZGF0ZV9pbnRha2VfY29tcGxldGVk').value = pika_js["completed_date"];
      // Case Zip Code
      document.getElementById('Y2FzZV96aXBfY29kZQ').value = pika_js["case_zip"];
      // Calculated Poverty Rate from Assets Screen
      document.getElementById('Y2FsY19wb3ZlcnR5').value = pika_js["poverty"];
      // Adjusted Poverty Rate from Liabilities Screen
      document.getElementById('YWRqX3BvdmVydHk').value = pika_js["recalc_poverty"];
      // Minor Children
      document.getElementById('bWlub3JfY2hpbGRyZW4').value = pika_js["children"];
      // Is applicant receiving any public benefits?
      document.getElementById('cHVibGljX2JlbmVmaXRz').value = pika_js["public_benefits_recipient"];
      // Problem Code
      document.getElementById('cHJvYmxlbV9jb2Rl').value = pika_js["problem"];
      // Special Problem Code
      document.getElementById('c3BlY2lhbF9wcm9ibGVtX2NvZGU').value = pika_js["sp_problem"];
      
      //this section un-squishes the docassemble interview when embedded in a Pika tab
      // div with dabody class - remove col, add container-fluid
      $(".dabody").removeClass("col");
      $(".dabody").addClass("container-fluid");

      // class span8, replace with container-fluid
      $(".span8").addClass("container-fluid");
      $(".span8").removeClass("span8");

      // id page_content, change container to container-fluid
      $('#page_content').addClass("container-fluid");
      $('#page_content').removeClass("container");
       </script>

    ---

</details>

<details>
	<summary>Connected Airtable databases</summary>
	
<br>	
This section is not directly connected to Airtable, but the Pika variables collected here are listed in the [facts table of the Legal Objects Library](https://airtable.com/shromaQ1J1QXNO5n2).	
    
    
</details>

## Selecting Specific Issues and Clones

The interview allows you to pick the specific legal issue by selecting subsets within an issue and a "clone" issue when appropriate.  A clone issue is the same issue that has different information because of the different jurisdiction or the stage of the problem.

<details>
	<summary>Software issues</summary>
	
###### Software issues
	1. Get data from related parties to the case
	   * link to issues
	2. Add in explanation about 1 and 0 as True and False
	   * link to issues
</details>

<details>
	<summary>Features Requests</summary>
	
###### Features Requests
	1. Pull in data from other sources
	   2. Court dockets
	   3. Property lists
	   
</details>

<details>
	<summary>How it works in docassemble</summary>
	
<br>	
The interview needs to complete apps.issues, a list of

The first issue - the "Top" issue - is added automatically.  This is the issue object for all types of legal objects, with subsets like "Housing", "Family".  We can add the 'Top' issue by using the issue2aid dictionary in the LegalObjectsLibrary_dictionary.yml.

	---
	code: |
	  app.issues.there_are_any = True
	---
	code: |
	  app.issues[0].a_id = issues2aid['Top']
	---

</details>

<details>
	<summary>Connected Airtable databases</summary>
	
<br>	
Issue Objects are in the LegalObjectLibrary base in the issues tab. [Here is a viewy]().	
    
    
</details>


## Finding Legal Defenses

If an

Instead of subsets, LegalObjects have elements

<details>
	<summary>Software issues</summary>
	
###### Software issues
	1. Get data from related parties to the case
	   * link to issues
	2. Add in explanation about 1 and 0 as True and False
	   * link to issues
</details>

<details>
	<summary>Features Requests</summary>
	
###### Features Requests
	1. Pull in data from other sources
	   2. Court dockets
	   3. Property lists
	   
</details>

<details>
	<summary>How it works in docassemble</summary>
	
<br>	
The app.legal_objects DAList is first populated by any Legal Objects associated with an IssueObject that was selected.

	code: |
	  for issue in app.issues:
		if hasattr(issue,'legalObjects'):
		  for legOb in issue.legalObjects:
		    app.legal_objects.append(legob_from_a_id(legOb))
	  app.legal_objects.gathered = True
	comment: |
	  Adds LegalObjects to issues
	---

</details>

<details>
	<summary>Connected Airtable databases</summary>
	
<br>	
Issue Objects have a field legalObjects, which is a list of Airtable ids of rows in the legalobjects tab.

Legal Objects are in the LegalObjectLibrary base in the legalobjects tab. [Here is a viewy]().	
    
    
</details>


## Matching Protocols

The interview allows you to pick the specific legal issue by selecting subsets within an issue and a "clone" issue when appropriate.  A clone issue is the same issue that has different information because of the different jurisdiction or the stage of the problem.

<details>
	<summary>Software issues</summary>
	
###### Software issues
	1. Get data from related parties to the case
	   * link to issues
	2. Add in explanation about 1 and 0 as True and False
	   * link to issues
</details>

<details>
	<summary>Features Requests</summary>
	
###### Features Requests
	1. Notification to advocate about "new" issue or clone.
	   
</details>

<details>
	<summary>How it works in docassemble</summary>
	
<br>	
Infosheets are made

	---
	code: |
	  app.issues.there_are_any = True
	---
	code: |
	  app.issues[0].a_id = issues2aid['Top']
	---

</details>

<details>
	<summary>Connected Airtable databases</summary>
	
<br>	
Issue Objects are in the LegalObjectLibrary base in the issues tab. [Here is a viewy]().	
    
    
</details>



## Creating Information Sheets

The specific legal issue leads you to the specific legal information that is most helpful.

The first time a new issue, or a new clone of an existing issue, an advocate will be presented with legal information about the .  The advocate can organize this information that is most understandable, 

### Gathering
### Next Steps and Options



<details>
	<summary>Software issues</summary>
	
###### Software issues
	1. Get data from related parties to the case
	   * link to issues
	2. Add in explanation about 1 and 0 as True and False
	   * link to issues
</details>

<details>
	<summary>Features Requests</summary>
	
###### Features Requests
	1. Send notification to advocate when there is an issue that isn't completed
	   
</details>

<details>
	<summary>How it works in docassemble</summary>
	
<br>	
The interview needs to complete apps.issues, a list of

The first issue - the "Top" issue - is added automatically.  This is the issue object for all types of legal objects, with subsets like "Housing", "Family".  We can add the 'Top' issue by using the issue2aid dictionary in the LegalObjectsLibrary_dictionary.yml.

	---
	code: |
	  app.issues.there_are_any = True
	---
	code: |
	  app.issues[0].a_id = issues2aid['Top']
	---

</details>

<details>
	<summary>Connected Airtable databases</summary>
	
<br>	
Issue Objects are in the LegalObjectLibrary base in the issues tab. [Here is a viewy]().	
    
    
</details>
