Immediate Termination Workflow

This workflow is triggered via Launchpad and uses identity information entered through an interactive form to process terminations. 

As only administrators have the privilege to change a user’s lifecycle state in SailPoint Identity Security Cloud (ISC), this workflow provides an alternative approach without granting admin access to end users. The workflow can be created using an admin or break-glass account PAT and exposed through Launchpad, allowing authorized end users or required teams to initiate termination requests securely without direct administrative privileges

It evaluates the user’s current lifecycle state and performs the following actions:

1. If the lifecycle state is Active, it transitions the identity to Terminated.
2. If the lifecycle state is Prehire, it transitions the identity to Rescinded.
3. If the identity is already Terminated or Rescinded, the workflow stops further processing.
4. The workflow also validates that the identity does not originate from a Non-Person authoritative source.
5. The workflow uses two forms: the first form is used to capture the identity information, and the second form displays the identity details for verification before processing.

Required Modifications

Please update the following as needed:
1. Modify the lifecycle state names used in the Compare String operators ("**Check if user is already in any of the inactive lifecycle state**", "**Check if user is in active lifecycle state**", "**Check if user is in prehire lifecycle state**").
2. Update the tenant name, client ID, client secret, and lifecycle state IDs in the HTTP Request action ("**Change user's lifecycle state to terminated**", "**Change user's lifecycle state to rescinded**").
3. Update the recipient email address and email content to align with your requirements in the Send Email action ("**Send success email**", "**Send failure email**").
4. Update the authoritative source ID in "**Check if user belongs to Non Person Auth Source**" step, for the source where termination of users is not required, applicable to non-person identities. (This step is optional and may be omitted if not required.).
5. Modify the forms ("**Emergency Termination - User Details Form**", "**Emergency Termination - User Selection Form**") as required to meet your specific business and validation needs.
6. Modify the form inputs as required in the "**Display user details Form**" step.


If you still need assistance, feel free to reach out to me on the community. My username is UjjwalJain

