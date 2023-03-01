.. _Usage:

Usage
=========

Terminal based Usage
-------------------------
Setup Global User in Terminal
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. code-block:: bash
    
    $ git config --global user.name "FIRST_NAME LAST_NAME"
    $ git config --global user.email "MY_NAME@tu-dresden.de" 

Clone Remote Repository
~~~~~~~~~~~~~~~~~~~~~~~~~~
Clone the repository using the HTML link from the clone option in GitLab.

.. code-block:: bash

   $ git clone ssh://git@141.30.80.100:7999/Group/SubGroup/project.git

How it works
~~~~~~~~~~~~~~~~~

The git add and git commit commands compose the fundamental Git workflow. These are the two commands that every Git user needs to understand, regardless of their team’s collaboration model. They are the means to record versions of a project into the repository’s history.

Developing a project revolves around the basic edit/stage/commit pattern. First, you edit your files in the working directory. When you’re ready to save a copy of the current state of the project, you stage changes with git add. After you’re happy with the staged snapshot, you commit it to the project history with git commit. The git reset command is used to undo a commit or staged snapshot.

In addition to git add and git commit, a third command git push is essential for a complete collaborative Git workflow. git push is utilized to send the committed changes to remote repositories for collaboration. This enables other team members to access a set of saved changes.


Add changes to Remote Repository
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
whenever the code is modified you can always add them to you git.

.. code-block:: bash 

   $ git add .

Commmit Changes 
~~~~~~~~~~~~~~~~~~~~~

Commit set a message about the changes you were done. The commit also saves a revision of the code and you can revert the code to any version anytime in one click.
A commit is kind of 'object' in git, and identifies and specifies a 'snapshot' of the branch at the time of the commit.

.. code-block:: bash

   $ git commit -m "message"

Push changes to Remote
~~~~~~~~~~~~~~~~~~~~~~~~~~

The git push command is used to upload local repository content to a remote repository. Pushing is how you transfer commits from your local repository to a remote repo. It's the counterpart to git fetch, but whereas fetching imports commits to local branches, 
pushing exports commits to remote branches. Remote branches are configured using the git remote command. Pushing has the potential to overwrite changes, caution should be taken when pushing.

for git deteched enviornements you have to use

.. code:: bash

   $ git push origin HEAD:<target branch>

for pushing to an empty repositories use:

.. code-block:: bash

   $ git push --set-upstream origin master

General schema for git push:

.. code-block:: bash

   $ git push <remote> <branch>

Setting up an empty repository
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
A Git repository is a virtual storage of your project. It allows you to save versions of your code, which you can access when needed. 

You'll first cd to the root project folder and then execute the git ``init`` command.

.. code-block:: bash
   
   $ cd /path/to/your/existing/code 
   $ git init

Pointing git ``init`` to an existing project directory will execute the same initialization setup as mentioned above, but scoped to that project directory.

``git init <project directory>``

Ignoring files
~~~~~~~~~~~~~~~

Ignored files are tracked in a special file named ``.gitignore`` that is checked in at the root of your repository. There is no explicit git ignore command: instead the ``.gitignore`` file must be edited and committed by hand when you have new files that you wish to ignore. 
``.gitignore`` files contain patterns that are matched against file names in your repository to determine whether or not they should be ignored.



Creating branch and other related functions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A branch represents an independent line of development. Branches serve as an abstraction for the edit/stage/commit process. You can think of them as a way to request a brand new working directory, ``staging area``, and ``project history``. 
New commits are recorded in the history for the current branch, which results in a fork in the history of the project.
It's important to understand that branches are just pointers to commits. When you create a branch, all Git needs to do is create a new pointer, it doesn't change the repository in any other way. 

The ``git branch`` command lets you **create, list, rename, and delete branches**. It doesn't let you switch between branches or put a forked history back together again. For this reason, ``git branch`` is tightly integrated with the ``git checkout`` and ``git merge`` commands.

List all of the branches in your repository. This is synonymous with:

.. code-block:: bash 

   $ git branch --list

Create a new branch called ``＜branch＞``. This does not check out the new branch. 

.. code-block:: bash

   $ git branch -d <branch>

Delete the specified branch. This is a **“safe”** operation in that Git prevents you from deleting the branch if it has unmerged changes. 

.. code-block:: bash

   $ git branch -D <branch>


VS Code Tutorial for gitlab tools
-----------------------------------

Clone Remote Repository
~~~~~~~~~~~~~~~~~~~~~~~~~~


Add changes to Remote Repository
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Commmit Changes 
~~~~~~~~~~~~~~~~~~~~~


Push changes to Remote
~~~~~~~~~~~~~~~~~~~~~~~~~~


Create Repository/Projects and Groups
--------------------------------------------------

.. contents::
   :local:
   :depth: 1
