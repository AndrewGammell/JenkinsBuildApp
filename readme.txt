This project is for testing jenkins only. currently setting up hooks for jenkins builds to be triggered.

Polling of repo every minute (Working).

Polling of repo on post-push (Not Triggering) Can't be done locally using git hooks as git does not have a post-push hook.
		However the same thing can be achieved using Git WebHooks.
		
Polling of repo on post-commit (Giving error "error: cannot spawn .git/hooks/post-commit: No error"). 
		Placing a shebang -> #!/bin/sh at the top of the post-commit hook fixed the issue (Working).
		
Polling of repo using WebHooks to trigger the build (Working).
		Issue to keep in mind is that when running jenkins on localhost the /github-webhook/ url is not exposed to the internet. 
		so using ngrok will tunnel it back to jenkins triggering the build.