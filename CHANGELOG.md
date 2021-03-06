## Change Log

### 1.0.0
Complete rewrite in ES2015.

* Promise-ified the API
* Auto-generation of documentation
* Modularized codebase
* Refactored tests to run primarily in mocha

#### Breaking changes
Most of the breaking changes are just methods that got renamed. The changes to `User` and `Organization` are deeper
changes that now scope a particular `User` or `Organization` to the entity they were instantiated with. You will need
separate `User`s to query data about different user accounts.

* `Github.getOrg` → `Github.getOrganization` and requires an organization name.
* `Github.getUser` now requires a username.
* `Issue.comment` → `Issue.createIssueComment`
* `Issue.create` → `Issue.createIssue`
* `Issue.edit` → `Issue.editIssue`
* `Issue.get` → `Issue.getIssue`
* `Issue.list` → `Issue.listIssues`
* `Repository.branch` → `Repository.createBranch`
* `Repository.collaborators` → `Repository.getCollaborators`
* `Repository.compare` → `Repository.compareBranches`
* `Repository.contents` → `Repository.getContents` and now takes an argument for the content type
* `Repository.delete` has been removed.
* `Repository.editHook` → `Repository.updateHook`
* `Repository.editRelease` → `Repository.updateRelease`
* `Repository.getCommit` no longer takes a branch as the first argument
* `Repository.getPull` → `Repository.getPullRequest`
* `Repository.getRef` now returns the `refspec` from GitHub's API.
* `Repository.getSha` now returns the same data as GitHub's API. If the reqeusted object is not a directory then the
   response will contain a property `SHA`, and if the reqeusted object is a directory then the contents of the directory
   are `stat`ed.
* `Repository.getStatuses` → `Repository.listStatuses`
* `Repository.listPulls` → `Repository.listPullRequests`
* `Repository.postBlob` → `Repository.createBlob`
* `Repository.postTree` → `Repository.createTree`
* `Repository.read` remove in favor of `Repository.getContents`
* `Repository.remove` → `Repository.deleteFile`
* `Repository.show` → `Repository.getDetails`
* `Repository.write` → `Repository.writeFile`
* `Search.code` → `Search.forCode`
* `Search.issues` → `Search.forIssues`
* `Search.repositories` → `Search.forRepositories`
* `Search.users` → `Search.forUsers`
* The Search API no longer takes a string, it now takes an object with properties `q`, `sort`, and `order` to make the
   parts of the query easier to grok and to better match GitHub's API.
* `User.gists` → `User.getGists`
* `User.notifications` → `User.getNotifications`
* `User.orgRepos` → `Organization.getRepos`
* `User.orgs` → `User.getOrgs`
* `User.repos` → `User.getRepos`
* `User.show` → `User.getProfile` and no longer takes filtering options
* `User.userStarred` → `User.getStarredRepos`
