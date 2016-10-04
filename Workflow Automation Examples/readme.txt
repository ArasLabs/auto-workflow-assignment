Workflow Automation Examples

This package includes four self-contained examples of workflow capabilities.

Setup Instructions:
 1) Import this package using the SolutionsUpgrade Import tool (http://www.aras.com/communityprojects/?projectid=DD32FF42D8B14CB28CD4732AAF2F5349)
 2) Ensure the SMTP server is set up properly in InnovatorServerConfig.xml
 3) Edit the email address of the admin user to use your email address
 


Workflow Assignment Example

 Description:
  Demonstrates dynamic workflow assignments based on properties of the controlled item
 
 Usage:
  1) Log in as to Innovator as admin
  2) Create a new "Workflow Assignment Example" item (under Workflow Examples in the TOC)
  3) Set one or more of the Reviewer properties on the form to an Identity (e.g. Innovator Admin)
  4) Save/Unlock/Close the item
  5) Check the InBasket - assignments should appear for each chosen Identity
  6) Open the Workflow Process that was created to see the assignments and voting weights
  
 How it works:
  A method is attached to the activity as an OnActivate server event (the activate event is fired 
  before assignments are checked, so this is the best place to do dynamic assignments).  When the 
  activity is activated, the method finds the controlled item, reads the Reviewer properties and 
  creates an assignment for each.  The voting weight is automatically set such that all specified 
  reviewers must vote for the activity to complete.
  
  

Workflow Branching Example

 Description:
  Demonstrates automatic workflow branching based on a property of the controlled item
 
 Usage:
  1) Log in as to Innovator as admin
  2) Create a new "Workflow Branching Example" item (under Workflow Examples in the TOC)
  3) Set the Plant property to any of the listed values
  4) Save/Unlock/Close the item
  5) Check the InBasket - an activity should appear for the chosen plant
  6) Open the Workflow Process that was created to see the branching that occurred
  
 How it works:
  A method is attached to an automatic activity as an OnActivate server event.  When the workflow
  is started, the automatic activity is activated and the method finds the controlled item.  It
  then reads the Plant property, finds the corresponding path and sets that path to be the default.  
  The activity then closes and the default path is followed.
  


Workflow EMail Example

 Description:
  Demonstrates workflow notifications
 
 Usage:
  1) Log in as to Innovator as admin
  2) Create a new "Workflow EMail Example" item (under Workflow Examples in the TOC)
  3) Save/Unlock/Close the item
  4) Check the InBasket - a new activity should appear
  5) Check your email for the notifications
  
 How it works:
  Two email items are attached as OnActivate notifications to All Assignments.  The simple email
  uses the string "${Item/item_number}" to show the controlled item's number property in the body
  of the email.  The other email uses a query string to get properties of both the activity and
  the controlled item.
  


Workflow Launch Example

 Description:
  Demonstrates the launching of a workflow from a server event or action.
 
 Usage:
  1) Log in as to Innovator as admin
  2) Create a new "Workflow Launch Example" item (under Workflow Examples in the TOC)
  3) Save/Unlock/Close the item
  4) Edit the item and check the Launch Workflow box
  5) Save/Unlock/Close the item
  5) Check the InBasket - a new activity should appear
  6) Repeat steps 2 & 3
  7) Choose the item and run the "Workflow Launch Example" action (under the Actions menu)
  8) Check the InBasket - a new activity should appear
  
 How it works:
  A method is attached to the ItemType as an OnAfterAdd/OnAfterUpdate server event.  When the item is
  saved with the Launch Workflow property set to 1, the method finds the Workflow Map by name, then 
  instantiates and starts it.  The same method is attached to the ItemType as an action, allowing the 
  workflow to be launched using a menu choice.
  
