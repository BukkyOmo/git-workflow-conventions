An extension of the Andela Engineering Playbook(https://github.com/andela/engineering-playbook) as used by Hall Of Fame that can be found at:

Welcome to the hof-conventions wiki!
### Table of Contents
***
1. [Commit Message](#commit-message)
2. [Git Workflow](#git-workflow)
3. [Pull Requests](#pull-request)
4. [Branch Naming](#branch-naming)
5. [Style Guide](#style-guide)
6. [Documentation](#documentation)
7. [API Responses](#api-responses)

### Commit Message
***
A commit message consists of a **header**, a **body** and a **footer**, separated by a blank line.

Avoid commit message lines longer than 100 characters

#### Message Header
The message header is a single line that contains a succinct description of the change containing a **type**, an optional **scope** and a **subject**.

##### `type`
This describes the kind of change that this commit is providing.
* feat (feature)
* fix (bug fix)
* docs (documentation)
* style (formatting)
* refactor (updating method of doing things)
* test (when adding missing tests)
* chore (maintain)

##### `scope`
The scope can be anything specifying the place of the commit change. For example **authorization**, **authentication**, etc...

##### `subject`
This is a very short description of the change.
* use imperative, present tense: “change” not “changed” nor “changes”
* don't capitalize the first letter
* no dot (.) at the end

#### Message Body
Just as in `subject` use imperative, present tense: “change” not “changed” nor “changes”

http://365git.tumblr.com/post/3308646748/writing-git-commit-messages

http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html

#### Message Footer
***
```
[(Finishes|Fixes|Delivers) #Github Issue number]

```
#### Message Example
```
feat(authentication): implement authentication of users
- implement log in function
- ensure only valid users can access resources
[Delivers #119]
```
***
### Pull Request

#### Pull Request Title

The Pull Request title should be named using the following format:

```
Short Task Description
```

#### Pull Request Description

The description of the PR should contain the following headings and corresponding content in Markdown format.

```
What does this PR do?

Description of Task to be completed?

How should this be manually tested?

Any background context you want to provide?

(Finishes|Fixes|Delivers) <Link to GitHub issue associated with pull request>

Screenshots (if appropriate)
```
***
### Branch Naming
Branches created should be named using the following format:

`{story type}-{story summary}-{issue number/story id}`
story type - Indicates the context of the branch and should be one of:

ft == Feature
bg == Bug
ch == Chore
story summary - Short 2-3 words summary about what the branch contains

Example

ft-resources-rest-endpoints-24

***
### Git Workflow
We will be using the Feature Branch Workflow.

There will be a main repository for the project which has the following:
- A master branch - This is reserved for production ready code
- A develop branch - This is where all complete features branches will be merged into. 

The core idea is that all feature development should take place in a dedicated branch instead of the develop branch

The workflow will be as follows:
* Create a new branch off of the develop branch, remember to conform to the [branch naming convention](https://github.com/andela/engineering-playbook/blob/master/5.%20Developing/Conventions/readme.md#branch-naming)
* When making any changes, push to the feature branch you created.
* Create a pull request against the develop branch..Remember to conform to the [PR naming](#pull-request) convention.

Further information on this workflow can be found at:

https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow

***
### Style Guide

We will be using the PEP-8 styling as described in:

https://www.python.org/dev/peps/pep-0008/

***
### Documentation

To ease documentation, we will use Sphinx which automatically generates documentation from docstrings:

http://www.sphinx-doc.org/en/stable/contents.html

***
### API Responses

We will return JSON objects in the JSend format to ensure consistency.

A basic JSend-compliant response with data(after a successful response) would look like:

```
{
'status': 'success',
'data': {
         'datum_1': 'Blah blah...',
         'datum_2': 'Blah blah...'
        }
}
```
A basic JSend-compliant response after an error is encountered:

```
{
'status': 'error',
'error': 'error type'
'message': 'Blah blah...'
}
```

More on JSend can be found at:

https://labs.omniti.com/labs/jsend
