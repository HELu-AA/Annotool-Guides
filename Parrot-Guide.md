<h1 align="center">
    Project Parrot 🦜
</h1>
<b> An elegant solution for annotation in Google Sheets.</b>
<h2>Annotation Workflow ✏️</h2>
<b>To get started annotating in Parrot, follow these steps:</b>
<ol>
<li>Open the link and start your queue by clicking the <code>START</code> button.</li>
<li>Follow the task instructions, using the instructions button if you need a refresher. Hover over the section labels to display a tooltip with some basic instructions on that section.</li>

> *(Tip: The purple rewind button allows you to see the original text of a column, including special markdown characters.)*
<li>If you feel you cannot complete a task, click the <code>SKIP</code> button in the footer towards the right side.</li>
<li>Once you have completed the task, click the green <code>SUBMIT</code> button in the bottom right corner. If you have missed a mandatory section, you will get a pop-up explaining what you missed and the section will be highlighted in red.</li>
</ol>
<b> Repeat steps 2 through 4 until you see a message stating that your queue is finished.</b>
<br/>
<br/>
<b>If you made a mistake and would like to edit one of your previous responses, follow these steps:</b>
<ol>
<li>Click the home icon in the bottom left to return to the home page.</li>
<li>Click the <code>BROWSE</code> button to view a list of completed tasks.</li>
<li>Find the row you want to edit and click on the <code>rowID</code>, highlighted blue.

> <i>(Tip: you can search for your email or name to find it faster, and click on any row to preview its prompt)</i>
</li>
<li>Make the necessary edits to your task, and click the <code>SAVE</code> button.</li>

> *If you click the* `SEND BACK` *button the task will be reinserted at the top of your queue*
</ol>

<h2>QA Workflow 🔍</h2>
<b>To QA annotator completions, follow these steps:</b>
<ol>
<li>Open the link and click the <code>BROWSE</code> button to open the QA menu.</li>
<li>Find the row you want to QA, rows that have not been QAed yet are marked with an exclamation point icon, otherwise they show the email of the annotator who has QAed the row.</li>
<li>Optionally, search for an annotator name and use the prompt previews visible by clicking on a row in the table.</li>
<li>Click the <code>rowID</code>, highlighted in blue, to access the QA editor. Make any needed edits and leave relevant feedback in the QA comments box.</li>
<li>If you would just like to edit the task and not send it back to the original annotator, click the <code>SAVE</code> button. Otherwise, click the <code>SEND BACK</code> button.

> *Clicking* `SEND BACK` *will remove the task from the browse list until it is completed by the annotator again*
</ol>
<b>Repeat steps 2 through 5 until you are finished QAing.</b>
<h2>Setting up the Interface ⚙️</h2>

<b>To set up a project using Parrot begin with these steps:</b>

> [!NOTE]  
> Attempting to use the Setup Dashboard from a browser signed into multiple Google accounts **may** cause issues for some users when trying to submit a configuration. The error will result in the user being stuck on a loading screen after pressing the <code>Configure</code> button. If this occurs, the recommended path of action is to try submitting the configuration from an Incognito/Private tab where all other accounts are signed out by default. If the issue persists please contact a project maintainer.  

<ol>
<li>Create a copy of the Parrot Template</li>
<li>Copy and paste your task spreadsheet into the data tab</li>
<li>Set the sheet to editable and set General Access to Editor</li>
<li>Click the <code>Parrot</code> button in the toolbar followed by the <code>Configure Sheets Interface</code> button to launch the Setup Dashboard  
    
> <i>You may be asked to provide permissions to the script before being able to open the interface. Please authorize using your Cohere email and then open the interface.</i>
</li>

<li>Within the Setup Dashboard, a horizontal list of all columns present in the <code>data</code> will be displayed</li>
<li> You must choose a column type from the table below for each of these columns. <ul> <li>There must only be one instance of each of the following column types:   <code>Annotator</code>,  <code>Row ID</code>,  <code>QA Annotator</code>, <code>QA</code> and <code>Task ID</code>.</li><li>All of the column types listed above with the exception of <code>Task ID</code> are necessary for the interface to function. If you do not configure at least one column for each of the column types listed above, the dashboard will automatically create additional columns of those types for you on submission.</li></ul></li>

<li>Select Mandatory and Rated where applicable.
<ul><li>Selecting Mandatory will enforce user input for the corresponding input field.</li><li>Selecting Rated will allow the user to provide a rating in addition to the specified input type.</li></ul></li>

<li>Optionally enter Additional Instructions which provide extra context to the annotator via tooltips in the interface.</li>
<li>Click on <code>Configure</code> to submit your configuration</li>

</ol>

> [!IMPORTANT]  
> To add columns to the data tab after configuring please use the <code>Add a new column</code> button within the Setup dashboard. Adding new columns while the interface is being used by annotators may cause issues when writing to the sheet. The best course of action is to inform all annotators to pause using the interface, once the changes have been made and the new configuration has been submitted all annotators using the interface should refresh their instances.

| Column Type  | Info                                                                                                                                                                                                                                   |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Row ID       | Unique row ID's. A new column of this type will be automatically created if none are present on submission.                                                                                                                                                                         |
| Task ID      | Unique task IDs, for use with multi-turn tasks                                                                                                                                                                                        |
| Annotator    | Annotator email column. A new column of this type will be automatically created if none are present on submission.                                                                                                              |
| Prompt       | Prompt column, will appear on the <code>left hand</code> side of the interface. Used as the preview text within the browse interface.                                                                                                  |
| Response     | Response column, will appear on the <code>right hand</code> side of the interface.                                                                                                                                                     |
| Read         | Information to be read by the user, will appear on the <code> left-hand </code> side of the interface.                                                                                                                                   |
| Write        | Input field for writing information, will appear on the <code>left hand</code> side of the interface.                                                                                                                                  |
| Rewrite      | The Input field for re-writing pre-existing information, will appear on the <code> right-hand </code> side of the interface.                                                                                                                 |
| Better       | Used in tandem with <code>Worse and Rating</code>, indicates which column will store the better completion of all rated responses within the interface. The **higher** rating value will indicate the **better** completion.           |
| Worse        | Used in tandem with <code>Better and Rating</code>, indicates which column will store the worst completion of all rated responses within the interface. The **lower** rating value will indicate the **worse** completion.             |
| Checkbox     | Checkbox column types are used when a checkbox data validation is present in the corresponding column. Checkboxes are sorted by <code>Checkbox Groups</code>, allowing for the bundling of related data within the UI. |
| Checkbox Group     | A special column type which represents and labels a grouping of checkboxes. **Every checkbox** must have an associated checkbox group.  |
| Hidden       | Indicates a column that is meant to be hidden from view in the interface. **If a column is not set to another type, this should be the used type.**                                                                                    |
| Dropdown     | Used when a dropdown data validation is present in the corresponding column. **Dropdowns are single choice.** The dropdown within the interface will directly pull its choices from the data validation of its column.                 |
| QA           | Column for storing QA comments per row                                                                                                                                                                                                 |
| QA Annotator | The column where submitted QA annotator emails will be stored                                                                                                                                                                              |

<b>To create a link to the interface follow these steps:</b>
> [!IMPORTANT]  
> Ensure that a valid configuration has been submitted before attempting to create a link

<ol>
<li>Click the <code>Extensions</code> button in the toolbar followed by the <code>Apps Script</code> button to open the Apps Script Editor</li>
<li>In the top right of the editor find and click the <code>Deploy</code> button followed by the <code>New Deployment</code> button</li>
<li>Ensure the <b>type</b> is set to <code>Web app</code> on the left portion of the pop-up</li>
<li>Enter a description that reflects the name of the task, this will not be the name shown in the interface but is used for deployment tracking</li>
<li>Set the <code>Execute as</code> dropdown to <b>User accessing the web app</b> </li>
<li>Set the <code>Who has access</code> dropdown to <b>Anyone within Cohere</b> </li>
<li>Click the <code>Deploy</code> button and copy the newly created Interface URL at the bottom of the page</li>

    
</ol>


<h2>Stack 💻</h2>
<code>React</code><br/>
<code>Parcel</code><br/>
<code>Apps Script</code><br/>
<code>Google Sheets</code>
