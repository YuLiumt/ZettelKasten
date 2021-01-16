## Component Retrieval Language

The Component Retrieval Language (CRL) specifies where to find the components, how to retrieve them, and where to store them on the local file system. 

It is a plain text language using a `!` to indicate directives. The current required directives are:

- `!CRL_VERSION`
	- Indicates the current version of CRL used.
	- This must be the first non-comment line of each CRL file.
- `!TARGET`
	- It will specify the directory, in which the components for the current repository will be placed.
	- The CRL file is split into sections, with each section corresponding to a repository. The order of the sections is irrelevant, however each section must begin with `!TARGET`.
	- `!TARGET` may contain predefined constants i.e. `$ROOT`, which could represent the root directory for all of the components.
- `!TYPE`
	- Specifies the tool used to checkout the components.
	- Currently, cvs, svn, git, http, https, ftp, darcs, and hg are supported.
- `!URL`
	- Specifies the location of the repository for anonymous checkout.
	- `!URL` may contain variables `$1`, `$2`, etc, which will correspond to the directories in the path given by `!CHECKOUT`.
- `!CHECKOUT`
	- Specifies the components to checkout from the repository.
	- If there are multiple components to be checked out from a single repository, they must be separated by a `/` and separated by a newline. 
	- CRL supports comments prefaced with a `#`. Any trailing whitespace or comments will be ignored.

Additional optional directives include:

- `!DEFINE`
	- Contain any definitions i.e. `$ROOT`.
- `!NAME`
	- Specifies an alternate name for the component to be checked out.
- `!AUTHORIZATION_URL`
	- Specify a different location for an authenticated checkout.
	- `ANONYMOUS_USER` and `!ANONYMOUS_PASSWORD` will specify the login credentials for an anonymous cvs checkout from the repository.
	- They can be abbreviated as `!AUTH_URL`, `!ANON_USER`, and `!ANON_PASS`.
- `!REPOSITORY_PATH`
	- Specify the location of the item to be checked out within a repository.
	- It can consist of a file path, or `$1` or `$2`, and will essentially serve as a prefix to the checkout path when the script is looking for the checkout item.
	- `!REPOSITORY_PATH` can be abbreviated as `!REPO_PATH`.