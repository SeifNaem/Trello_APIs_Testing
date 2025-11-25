# Trello_APIs_Testing
End-to-End Scenario for Trello APIs (Automated in Postman)

This end-to-end scenario verifies the full lifecycle of Trello objects using REST APIs. It covers creating, updating, and deleting workspaces, boards, lists, cards, and checklists. After every operation, a GET request is issued to verify that the action was successful.
The whole flow is automated using Postman scripts and collection variables.

# Scenario Steps

# 1. Create a Workspace
 Send a POST request to create a new Trello workspace.
 
 Validate response status 200.
 
 Extract the created "workspaceId" and store it in collection variables.    

 GET workspace by ID to verify creation.

# 2. Create a Board inside the Workspace

POST to create a board associated with the workspace.

Validate response status 200 and extract "boardId".

GET the board to confirm it was created.

# 3. Create a List

POST to create a list on the created board.

Extract listId.

GET the list to ensure it exists and is linked to the correct board.

# 4. Create a Card

POST to create a new card under the selected list.

Extract cardId.

GET the card to validate successful creation.

# 5. Create a Checklist

POST to add a checklist to the created card.

Extract checklistId.

GET the checklist to verify creation.

# 6. Update Workspace Name

PUT request to update the workspace name.

GET the workspace to confirm the update.

# 7. Update List Name

PUT to rename the board.

GET the board to verify the new name.

# 8. Update Card Name

PUT request to change the list name.

GET list to confirm it was updated successfully.

# 9. Delete the checklist

DELETE request to remove the checklist.

GET the checklist to confirm deletion and status code 404.

# 10. Delete the card

DELETE request to remove the card.

GET the card to confirm deletion and status code 404.

# 11. Delete the board

DELETE request to remove the board.

GET the board to confirm deletion and status code 404.

# 11. Delete the workspace

DELETE request to remove the board.

GET the board to confirm deletion and status code 404.


# The entire workflow is automated using Postman Collections with:

Pre-request Scripts to generate authentication variables.

Environment Variables for dynamic IDs (workspaceId, listId, cardId, checklistId).

# Test Scripts to:

Validate response data.

Extract and store IDs automatically.

Check status codes and response messages.

Collection Runner to execute the full scenario automatically.

