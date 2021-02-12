#Exercise 7.1
##Create an AWS CodeCommit Repository and Submit a Pull Request
This exercise demonstrates how to use AWS CodeCommit to submit and merge pull
requests to a repository.
1. Create an AWS CodeCommit repository with a name and description. You do not
need to configure email notifications for repository events.
2. In the AWS CodeCommit console, select **Create File** to add a simple markdown file to test the repository.
3. Clone the repository to your local machine with HTTPS or SSH authentication.
4. Create a file locally, commit it to the repository, and push it to test the AWS CodeCommit.
5. Create a feature branch from the master branch in the repository.
6. Edit the file and commit the changes to the feature branch.
7. Use the AWS CodeCommit console to create a pull request. Use the master branch of the repository as the destination and the feature branch as the source.
8. After the pull request successfully creates, merge the changes from the feature branch with the master branch.

The pull request has been merged with the master branch, which can be confirmed by viewing the source code of the markdown file in the master branch.
