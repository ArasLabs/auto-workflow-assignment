# Automatic Workflow Assignment

The Automatic Workflow Assignment project demonstrates how to implement dynamic workflow assignments based on properties of the controlled item.

#### How it works
A method is attached to the activity as an OnActivate server event (the activate event is fired before assignments are checked, so this is the best place to do dynamic assignments).  When the activity is activated, the method finds the controlled item, reads the Reviewer properties and creates an assignment for each. The voting weight is automatically set such that all specified reviewers must vote for the activity to complete.

## Project Details

**Built Using:** Aras 11.0 SP7
**Browsers Tested:** Internet Explorer 11, Firefox 38 ESR, Chrome

> Though built and tested using Aras 11.0 SP7, this project should function in older releases of Aras 11.0 and Aras 10.0.

## Installation

#### Important!
**Always back up your code tree and database before applying an import package or code tree patch!**

### Pre-requisites

1. Aras Innovator installed (version 11.0 SPx preferred)
2. Aras Package Import tool
3. AutoWorkflowAssignment import package

### Install Steps

1. Backup your database and store the BAK file in a safe place.
2. Open up the Aras Package Import tool.
3. Enter your login credentials and click **Login**
  * _Note: You must login as root for the package import to succeed!_
4. Enter the package name in the TargetRelease field.
  * Optional: Enter a description in the Description field.
5. Enter the path to your local `..\AutoWorkflowAssignment\Import\imports.mf` file in the Manifest File field.
6. Select **aras.labs.WorkflowAutomationExamples** and **aras.labs.AutoWorkflowAssignment** in the Available for Import field.
7. Select Type = **Merge** and Mode = **Thorough Mode**.
8. Click **Import** in the top left corner.
9. Close the Aras Package Import tool.

You are now ready to login to Aras and try out Automatic Workflow Assignments.

## Usage

The Find Parent Package action is accessible from the Action menu in the Aras main window, the main grid context menu, and the Action menu in the Item tear-off window. The steps below show how to use the Find Parent Package action in the Aras main window Action menu.

1. Log in to Aras as admin.
2. Navigate to **Workflow Examples** in the table of contents (TOC).
3. Create a new Workflow Assignment Example item.
4. Set one or more of the Reviewer properties on the form to an Identity (ex: Innovator Admin)
5. Click **Save/Unlock/Close**.
6. Navigate to **My Innovator > My Inbasket** in the TOC.
7. Search for active "Do Something" assignments. An assignment should appear for each Identity chosen on the Workflow Assignment Example form.

To review the dynamically created assignments and voting weights, open the Work Item from one of the assignments. On the item form, select Views > Workflow from the main menu to view the workflow process.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

For more information on contributing to this project, another Aras Labs project, or any Aras Community project, shoot us an email at araslabs@aras.com.

## Credits

Original Aras community project written by Rob McAveney at Aras Corp.

Project rewritten for Aras 11.0 by Alexander Sklyarskiy. @asklyarskiy

Documented and published by Eli Donahue at Aras Labs. @elijdonahue

## License

Aras Labs projects are published to Github under the MIT license. See the [LICENSE file](./LICENSE.md) for license rights and limitations.
