=====================
Lesson 2 : Assignment
=====================

.. todo::
    Make this assignment consistent with the case study.
    Determine how to automatically test injected errors.

One of the challenges with the existing code base at HP Norton is the lack
of necessary debug information when issues occur.

Your task this week will be to incorporate logging into an
existing module so that we can trace what goes on as the module
runs. We are also going to use the debugger to identify and help resolve a
problem with that module.

Here is what you need to do:
----------------------------
#. Clone the PhyRe.py code and review it.
#. First you need to get it to at least start to run. Update it as needed.
#. Try as best you can to understand what the code is doing.
#. Now, start to insert logging statements to track the code's execution
#. Using the debugger, try to understand what is going on with the
   expected command line parameters. See if from the code and through
   watching variables and creating dummy parameters you can infer enough
   to get the program to run.
#. Add comments that describe your discoveries, additional things you need
#. to know and any other comments.

Requirements:
-------------

Submission:
-----------

Tips
----
- Think about what a developer would need by way of logging to help trace what
  has happened and gone wrong when the module is running.
- Log at different levels of severity based on your envisioned needs.
- Add details of your approach to logging to the module docstring to assist
  anyone who maintains the module.
- Be sure to document details of your fix from the debugging activity in
  your pull request.
