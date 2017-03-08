**********
Session 09
**********

.. figure:: /_static/django-pony.png
    :align: center
    :width: 60%

    image: http://djangopony.com/

Extending Django
================

.. rst-class:: large

Wherein we extend our Django blog app.

But First
---------

.. rst-class:: build left
.. container::

Agenda:

    .. rst-class:: build

    * Class website - where to find this week's materials
    * Status of our Django blog
    * Intro to Agile
    * Pair programming
    * Lightning Talks (Ninad Naik, Abdishu Hagi, Beatrice He, James Richardson)
    * Pair programming
    * Homework and plan for next week

.. nextslide::

.. rst-class:: build left
.. container::

    Class website - where to find this week's materials

    .. rst-class:: build

    * `The code <https://github.com/christyheaton/mysite_start_session09>`_
    * `HTML rendering of exercise <https://christyheaton.github.io/training.python_web/html/presentations/session09.html>`_
    * More resources below


Last Week
---------

Last week, we created a nice, simple Django microblog application.

.. rst-class:: build
.. container::

    Over the week, as your homework, you made some modifications to improve how
    it works.

    There's still quite a bit more we can do to improve this application.

    And today, that's what we are going to do.


Our Status
----------

Demo blog


Enhancement Ideas
-----------------

You and your partner can work on any of the following enhancements

Choose one to start with - if you finish it, start another!

Use your partner first to work with any issues that arise

Use the proposed resources, but you may still need to troubleshoot, research, and find other materials


Django Rest Framework
---------------------

Goals:

.. rst-class:: build
.. container::

    * User can visit a DRF "API View" page to create and retrieve posts and categories.
    * Your primary resource for this will be the `DRF documentation <http://www.django-rest-framework.org/#installation>`_ "installation" and "example" guides.


RSS Feed
--------

Goals:

.. rst-class:: build
.. container::

    * A user will be able to visit a page on your site and view an RSS list of posts, like `CNN's RSS feed of top stories <http://rss.cnn.com/rss/cnn_topstories.rss>`_.
    * Your primary resource will be `this example <https://docs.djangoproject.com/en/1.10/ref/contrib/syndication/#a-simple-example>`_ from the Django documentation.
    * You'll have to change a few things in order to adapt this example to our posts model.
    * For example, our posts don't have a "pub_date" field, but they do have another similar field.
    * And our posts don't have a description field, so the call to "item.description" will fail; you'll have to use another similar field.
    * Also, we don't have a view named 'news-item', our post-detail view has a different name, and it takes a kwarg instead of an arg.

Post Creation Form
------------------

Goals:

.. rst-class:: build
.. container::

    * User can visit a page on your site which presents a form that they can use to create a post.
    * The user should be able to at least specify the title and content of the post
    * If they can't choose the category then that's OK
    * Your primary resource will be `this example <https://tutorial.djangogirls.org/en/django_forms/>`_ from DjangoGirls
    * You might need to create a template similar to the template in the example
    * And you might need to specify the template name using a 'template_name' property
    * And check out the docs on `createview <https://docs.djangoproject.com/en/1.10/ref/class-based-views/generic-editing/#createview>`_ and `fromview <https://docs.djangoproject.com/en/1.10/ref/class-based-views/generic-editing/#formview>`_

All-Auth
--------

Django All-Auth and Facebook

Goals:

.. rst-class:: build
.. container::

    * Users can visit the Django-Allauth login page
    * The Django-Allauth login page includes a link to login with Facebook
    * They can use that link to login to Facebook
    * When a user logs in, they are directed to the main list page
    * When a user visits the main index/list page or the detail page they see a link to the allauth login page if they are not logged in
    * If they are logged in then they see a link to the logout page

Resources:

.. rst-class:: build
.. container::

    * `Django docs on allauth <https://django-allauth.readthedocs.io/en/latest/installation.html>`_
    * `A video on allauth <https://www.youtube.com/watch?v=1yqKNQ3ogKQ>`_


Something Else!
---------------

.. rst-class:: build
.. container::

    * Change the CSS
    * Some other enhancement that you like


Agile
-----

.. rst-class:: build
.. container::

    Alternatives to traditional project management

    A set of principles for software development

    Designed to help teams respond to unpredictability

    Emphasis on incremental iterative work cadences and empirical feedback

    `Scrum <https://www.scrumalliance.org/why-scrum>`_

    `Kanban <https://leankit.com/learn/kanban/what-is-kanban>`_

    `Pair Programming <https://www.agilealliance.org/glossary/pairing>`_

    (Source: http://agilemethodology.org/)


Pair Programming
----------------

.. rst-class:: build
.. container::

    Two programmers work at one workstation

    Driver - writes code

    Navigator - reviews code, observes, considers improvements or changes in direction

    The two programmers switch roles frequently


Preparation
-----------

In order for this to work properly, we'll need to have a few things in place.

.. rst-class:: build
.. container::

    **For the time being, all these actions should only be taken by one
    partner**.

    First, we'll start from a canonical copy of the microblog.  Make a fork of
    the following repository to your github account::

        https://github.com/christyheaton/mysite_start_session09.git

    Then, clone that repository to your local machine:

    .. code-block:: bash

        $ git clone https://github.com/<your_name>/mysite_start_session09.git


.. nextslide::

.. rst-class:: build
.. container::

    I'll make an announcement when its time to switch

    We'll take a break for lightning talks

    And hear your thoughts on Pair Programming at the end


Connect to Your Partner
-----------------------

Finally, you'll need to add your partner as a collaborator for your new
repository.

.. rst-class:: build
.. container::

    Go to the *settings* for your repository.

    Click the *collaborators* tab on the left side of the window (you'll need
    to enter your github password).

    Look up your partner by email address or github username.

    Add them.

    Then your partner can clone the repository to their desktop too.

While You Work
--------------

Now, when you switch roles during your work, here's the workflow you can use:

.. rst-class:: build
.. container::

    .. container::

        1. The current driver commits all changes and pushes to their repository:

        .. code-block:: bash

            $ git commit -a -m "Time to switch roles"
            $ git push origin master

    .. container::

        2. The new driver gets the changes:

        .. code-block:: bash

            $ git pull origin master

    3. The new driver continues working from where their partner left off.
    4. PROFIT.....


Pair Programming
----------------

.. rst-class:: large

Let's get started!


.. nextslide::

How did it go?


Homework
========

Next week, we will deploy your Django application to a server.

.. rst-class:: build
.. container::

    To help illustrate the full set of tools at our disposal, we'll go a bit
    overboard for this.

    We'll be setting up an HTTP server, proxying to a WSGI server serving your
    Django app.

    We'll do this all "In the cloud" using Amazon's `AWS`_ service.

    Before class starts, you'll need to accomplish a few non-programming tasks

.. _AWS: http://aws.amazon.com/free

Sign Up For AWS
---------------

Begin by going to the `AWS homepage`_ and clicking on the large button
that reads "Sign in to the Console".

.. rst-class:: build
.. container::

    On the sign-in page that appears, click the radio button for 'I am a new user.', fill in your email address, and then click through to begin the
    sign-up process.

    You will be required to provide credit card information.

    If you are still eligible for the AWS free tier, you will not incur any
    charges for work you do in this class.

.. _AWS homepage: http://aws.amazon.com


Set Up an IAM User
------------------

Once you've signed up for an account take the following actions:

* `Create an IAM user`_ and place them in a group with Power User access. (Search for PowerUser when selecting a policy for your group).

  * Set up Security Credentials for that IAM user.
  * Save these Security Credentials in a safe place so you can use them for class.

.. _Create an IAM user: http://docs.aws.amazon.com/IAM/latest/UserGuide/getting-setup.html

Prepare for Login
-----------------

* `Create a Keypair`_

  * Choose the 'US West (Oregon)' region since it's geographically closest to you.
  * When you download your private key, save it to ~/.ssh/pk-aws.pem
  * Make sure that the private key is secure and useable by doing the following command

    * ``$ chmod 400 ~/.ssh/pk-aws.pem``

* `Create a custom security group`_

  * The security group should be named 'ssh-access'
  * Add one custom TCP rule

    * allow port 22
    * allow addresses 0.0.0.0/0

.. _Create a Keypair: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html#having-ec2-create-your-key-pair
.. _Create a custom security group: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html
