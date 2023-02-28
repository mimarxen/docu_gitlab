
.. _Setup:

Setup
==========

Create Account
---------------
Visit the following link and create your account under the ``register now`` button.
When signing in, use your ``ZIH username`` as username and ``@tu-dresden.de`` email. You will have to wait for the administrator to allow you to log in for the first time, 
as you need to be verified by the admin.
On the first login, you won't have access to any repositories. Please ask your contact person or admin for access. 

..  code-block:: bash

    http://141.30.80.100:8080/

or via ssh access


.. code-block:: bash 

    ssh://git@141.30.80.100:7999/Group/SubGroup/repo.git

Software Requirements
------------------------------

The following softwares are required for this:

* `Git <https://git-scm.com/download/win>`__
* `VS Code <https://code.visualstudio.com/>`__
* `Git Graph <https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph>`__
* `GitLens — Git supercharged <https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens>`__
* `Git Extension Pack <https://marketplace.visualstudio.com/items?itemName=donjayamanne.git-extension-pack>`__
* `GitLab Workflow <https://marketplace.visualstudio.com/items?itemName=GitLab.gitlab-workflow>`__
* `Git Cheatsheet <https://marketplace.visualstudio.com/items?itemName=dzhavat.git-cheatsheet>`__ to use ```ctrl+shift+p``` and ```Open Git CheatSheet```



Setup SSH Keys
-----------------------------
To clone the repository, you must use ssh. (SSH or Secure Shell is a network communication protocol that enables two computers to communicate (c.f http or hypertext transfer protocol, which is the protocol used to transfer hypertext such as web pages) and share data.)

Now to access the ssh from your git bash. You need to set up ssh keys in your account. 

Open your Git Bash and go to your ssh folder

.. code-block:: bash

    $ cd ~/.ssh/

Generate ssh keys:

.. code-block:: bash

    $ ssh-keygen -t ed25519 -C "<comment>"

where the comment is your device id

Press ``Enter``. Output similar to the following is displayed:

.. code-block:: none
    
    $ Generating public/private ed25519 key pair.
    $ Enter the file in which to save the key (/home/user/.ssh/id_ed25519).

then type the password and press enter to leave the password blank. 

.. warning:: 
    When you type, the password won't be visible. 

Then type 

.. code-block:: bash
    
    $ cat id_ed25519.pub

and copy whatever is displayed in the next line. 

Log in to GitLab sesyn on your browser, and under the ``user settings > preferences > SSH Keys``, paste the info there and add a new key. 
You will see a file named ``id_ed25519``. This is your private, and you must never share this key anywhere. 

Advanced users who are comfortable with bash can now move forward to `Usage` section. 

Configure SSH to point to a different directory
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. code-block:: linux-config

    eval $(ssh-agent -s)
    ssh-add <directory to private SSH key>

Save these settings in the ``~/.ssh/config`` file. For example:

.. code-block:: linux-config

    # GitLab.com
    Host gitlab.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/gitlab_com_rsa

    # Private GitLab instance
    Host gitlab.company.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/example_com_rsa 

Setup VS Code for Development
------------------------------------
To set up vs code for development, we can set up GitLab access tokens. To use GitLab, you must be VPN or inside the building connected to LAN. 

Open your git bash and set up your GitLab credentials.

.. code-block:: bash
    
    $ git config --global user.name "FIRST_NAME LAST_NAME"
    $ git config --global user.email "MY_NAME@tu-dresden.de"

Open your account on the browser and go to ``user settings > preferences > Access Tokens`` here, give the token name and set the expiration date (blank for never).
Give all the scopes to this. 

.. warning:: 
    Then copy the generated key from the top. Do not lose this, as you cannot see it once you generate it. It's only visible during generations. 

Open your vs code and use ``ctrl+shift+p`` and type ``gl.addAccount`` and type the IP of the server 

.. code-block:: bash 

    http://141.30.80.100:8080

then paste your token there, and you will see a blue tooltip at the bottom stating that the account has been added successfully. 

.. contents::
   :local:
   :depth: 1
