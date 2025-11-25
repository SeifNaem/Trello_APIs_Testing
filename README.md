# Trello_APIs_Testing
End-to-End Scenario for Trello APIs (Automated in Postman)

This end-to-end scenario verifies the full lifecycle of Trello objects using REST APIs. It covers creating, updating, and deleting workspaces, boards, lists, cards, and checklists. After every operation, a GET request is issued to verify that the action was successful.
The whole flow is automated using Postman scripts and environment variables.

# Scenario Steps

# 1. Create a Workspace
    Send a POST request to create a new Trello workspace.
    Validate response status 200/201.
    Extract the created "workspaceId" and store it in collection variables.

# 2. Create a Board

# 3. Create a List

Send a POST request to create a list inside the previously created workspace (via board ID if required).

Validate status code.

Save the listId for next operations.

Create a Card

Use a POST request to create a card inside the created list.

Validate response and extract cardId.

Create a Checklist

Use a POST request to add a checklist to the created card.

Validate success and save the checklist.

Update Workspace Name

Send a PUT request to update the workspace name.

Verify updated details and response body.

Update List Name

Use a PUT request to rename the list.

Ensure the list name is updated correctly.

Update Card Name

Send a PUT request to modify the card name.

Validate that the card name has been changed successfully.

Delete the Card

Send a DELETE request using the cardId.

Confirm deletion with response code 200 and optional GET to verify it's removed.

Delete the List / Workspace (Optional Cleanup)

Delete remaining objects to keep environment clean.

Postman Automation

The entire workflow is automated using Postman Collections with:

Pre-request Scripts to generate authentication variables.

Environment Variables for dynamic IDs (workspaceId, listId, cardId, checklistId).

Test Scripts to:

Validate response schema.

Extract and store IDs automatically.

Check status codes and response messages.

Collection Runner to execute the full scenario as a single automated pipeline.

Optional: Newman to run the scenario in CI/CD for continuous API testing.
