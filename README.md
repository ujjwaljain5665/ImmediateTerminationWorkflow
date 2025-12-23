Immediate Termination Workflow

This workflow is triggered via Launchpad and uses identity information entered through an interactive form to process terminations. It evaluates the user’s current lifecycle state and performs the following actions:

1. If the lifecycle state is Active, it transitions the identity to Terminated.
2. If the lifecycle state is Prehire, it transitions the identity to Rescinded.
3. If the identity is already Terminated or Rescinded, the workflow stops further processing.
4. The workflow also validates that the identity does not originate from a Non-Person authoritative source.
5. The workflow uses two forms: the first form is used to capture the identity information, and the second form displays the identity details for verification before processing.

Required Modifications

Please update the following as needed:
1. Modify the lifecycle state names used in the Compare String operators.
2. Update the tenant name, client ID, client secret, and lifecycle state IDs in the HTTP Request action.
3. Update the recipient email address in the Send Email action.
4. Update the lifecycle state names in all Compare String operators (as applicable).
5. Modify the email content to align with your requirements.
6. Modify the forms as required to meet your specific business and validation needs.

If you still need assistance, feel free to reach out to me on the community. My username is UjjwalJain