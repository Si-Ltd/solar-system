GitHub Actions - Security Hardening

Let's have a look at a few good security practicies for using GitHub Actions features.

So we will start witht he sensitive information. So sensitive values should never be stored as plain text in the workflow files, but rather as secrets.
So secrets can be configured at the organization, repository, or environment level and allow you to store sensitive information on GitHub.
So secrets use Libsodium sealed boxes so that they are encrypted even before reaching GitHub.
So this occurs when the secret is submitted using the UI or through the REST API.
So to help prevent accidental disclosure, GitHub also uses a mechanism that attempts to mask any secrets that appear in the logs.

The second one is about OpenID Connect.
So the OpenID Connect feature allows your workflows to exchange short-lived tokens directly from your cloud provider.
GitHub Actions workflows are often designed to access a cloud provider such as AWS, Azure of GCP and in order to deploy software or to use the cloud services.
So before the workflows can access these resources, it will supply credentials such as a token or a password to the cloud provider.
These credentials are usually stored as secrets in GitHub. However, using hard-coded secrets requires you to create credentials in the cloud provider and then duplicat ethem in GitHub as a secret. 
So using OpenID Connect, you can take a different approach by configuring your workflow to request a short-lived access token directly from the cloud provider. Your cloud provider also needs to support OIDC on ther end as well.

And then we'll talk about the script injection attacks.
So when creating workflow actions, you should always consider whether your code might execute untrusted input from attackers.
This can occur when an attacker adds malicious commands or scripts to a context.
So when your workflow executes, these strings might be interpreted as code which in then executed on the runner.
So to expose secrets and sensitive data and you could also change the behavior of the workflow actions. *
So there are a number of different approaches available to help you mitigate the risk of script injections and we will see one of them in the upcoming session.

And finally, there are various numbers of security issues which can araise when you're using some third-party actions and GitHub Actions.
So some of the most common issues are the malicious code, vulnerabilities and insufficient permissions.
So talking about the malicious code, third-party actions could have malicious code which contains logic that could compromise your repositories.
Talking about vulnerabilities, third-party actions could have serious undisclosed vulnerabilities that could be exploited by attackers in the future.
And finally, talking about the insufficient permissions, third-party actions may require more permissions than they need which might again compromise your GitHub account.

So to mitigate the issues with respect to these third-party actions, it is always recommended to use your own actions wherever applicable but this approach requires a considerable amount of effort as the actions need to be created and maintained by you.

The second option is to use a combination of your own actions and actions which are verified by GitHub.
So verified actions are third-party actions that have been verified and approved by GitHub.
This means that GitHub has reviewed the action code and determined that it is safe and does what it is supposed to do.
Verified actions are identified by a blue check mark next to the action name in the GitHub marketplace.

And finally, if there is no option left, we can also use the public or the community actions with caution.
So it is a good idea to review the action code to make sure that you understand what it is doing.
You can also pin the action to a specific commit to prevent malicious updates.
And finally, alwaysd use least privilege principle to only grant the action the permissions that it needs.


