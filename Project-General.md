## CHAP Project Documentation

__The information in this file is not fixed. It may change at any time. Announcements will be made on Teams for such matters.__ 
 <>
__Some steps in this documentation require special knowledge of JIRA and Github and as such, corresponding tutorial documents will be posted.__
___

### Creating new Projects
Since the main goal of CHAP is to complete as many projects as we can, a simple structure, yet strict should be defined when creating a new project to facilitate the integration of both the users and developers. 

#### How to create a new project:
- Make a github repo in our CHAP organization at : [CHAP's Github Org](https://github.com/chap-organization)
- Add the developers who are part of the project the repo and give them the correct permissions. The reason we do not give everyone access is to keep things under control, making sure that only the involved people have influence on the production code. 
- Make a corresponding JIRA project in our CHAP organization at : [CHAP's JIRA Org](https://chap-club.atlassian.net/jira/projects?selectedProjectType=software) 
- **Once the repo and the JIRA are done, the first thing to do is create a Comprehensive Readme.md for you Github Repo. It must be completed before any line of code is written.** 
    -  The Readme must contain the following information 
        1. Title of the project
        2. Developer list
        3. Scope of the project
        4. Tech Stack of the project
- In Git, create the main production branches, example : `develop` and add branch protection rules so that only specific people can merge to this branch. It represents the source of truth for your application and must only contain code that is fully working. No one should directly push to these branches as code must be merged from a pull request. 

### Guidelines to follow when working on a project
This section quickly describes some guidelines to follow in order to uniformalize our workflow. This will permit developers to easily join new teams and quickly start working without getting used to a whole new system.  

##### JIRA integration with GIT. 

 Jira integration with git offers many advantages to keep track of branches/commits and pull requests directly from JIRA. This greatly simplifies the visualization of the project progress and it facilitates the coordination of a team!!! For this integration, two things must be done: naming conventions and workflow. 
 
##### Naming conventions to follow
 1. `git Branches` should contain the issue number they are related to.    - if I work on a JIRA ticket called `PRO-8` then my branch must contain the issue name. Example : `PRO-8-fixing-side-bar` or for simplicity `PRO-8`. The need to add a title is redundant as the JIRA issue has all the description we need conserning the issue.
 2. `git Commits` should follow the same logic, they should contain the issue name in their message.
 Example of a commit message : `PRO-8 fixed the sidebar and implemented bootstrap responsivness.`
 3. `git Pull Requests` should also follow the same logic. When a PR is made, the name can be changed and for JIRA to recognize the PR, make sure that the issue name is also present in the PR name. 

##### Workflow 
The workflow defined here is in no way permanent, and can be changed very quickly if better alternatives are proposed. Please do voice yourself for such changes as it can benefit everyone to continuously upgrade our way of doing things!
___
The workflow as it is now is a 7 states workflow:
#### 1. Open (Start point)
###### Explanation of State:
Once an issue is created, it will automatically be placed in the open state. This state represents issues that are created but have yet to have someone assigned to them. They are "open" for people to take and place in their own stack of tasks to complete. 
Whenever someone drops an issue and removes himself from the assignee role leaving it `unassigned`, the issue must be placed in this state. 
###### Possible Transitions:
-> `To Do` : the assignee of the task has been assigned.

#### 2. To Do
###### Explanation of State:
Once an issue is assigned someone, it is put in `To Do` and it becomes the task of the developer to start it whenever he/she has the time. 
###### Possible Transitions:
-> `In Progress` Once the developers wishes to start, he must put the issue this state to tell others of his progress. 

#### 3. In Progress
###### Explanation of State:
The developer has started his task and is currently making it one of his priorities. Commits are being pushed to remote branch. 
###### Possible Transitions:
-> `Paused` The assignee has something blocking him from continuing the work and so has to pause it. <p></p>
-> `Dev Verifier`The assignee is satisfied with his changes and therefore submits a PR for the `dev verifier` to look at. 
#### 4. Paused
###### Explanation of State:
Developer has paused the state considering he has higher priorities tasks/events that are happening. 
###### Possible Transitions:
-> `In Progress` developer is resuming the completion of the task. 
#### 5. Dev Verifier
###### Explanation of State:
The `Dev Verifier` is the individual who reviews the PR related to this issue. He must therefore pull the branch from the remote and explicitely test the code done by the assignee to confirm whether the expectations were met or not. 
###### Possible Transitions:
-> `To Do` The verifier was not satisfied with the changes and the PR was refused and sent back to the developer. 
->`To Deploy` The verifier was satisfied with the changes and accepted the pull request. 
#### 6. To Deploy
###### Explanation of State:
This step comes right after a dev-verifier has approved changes from a PR. The code must now be merged with the production branches in Git. This state represents a "stand by" state, waiting for someone with access to merge the changes in. 
###### Possible Transitions:
-> `Done` The changes have been merged. 
#### 7. Done
The ticket issue has been resolved and merged with success into the production code!


### Conclusion 

This concludes this wiki regarding our projects and how they are structured with JIRA. If you have any questions, please ping the Executives of CHAP's club on teams. This document can always be updated and improved so don't hesitate to bring suggesions!!!!


