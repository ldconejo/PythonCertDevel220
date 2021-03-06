########
Activity
########

:TODO - This activity belongs to context managers, this lesson is on functional programming

The `Ballard Lockes <https://en.wikipedia.org/wiki/Ballard_Locks>`__ in
Seattle, Washington, are a limited, controlled resource. You have been
hired by the Army Corps of Engineers to help build a software control
system for the lockes. There are two lockes at the Ballard complex, one
small (30 x 150 feet, 8.5 x 45.7 meter) and one large (80 x 825 feet,
24.4 x 251.5 meter). There are a myriad ways in which different components
of the lockes represent limited resources with specialized subsystems,
and a missed or out-of-sequence step could mean disaster. For instance,
there are two sets of doors for each locke, one upstream and one down,
that cannot both be open at the same time; boats need to clear the doors
before they are closed and sealed; pumps need to be shut down before
doors are opened; tourists, who can get very close to observe the
action, need to be safely managed; the lockes themselves can only handle
a certain number of boats. At every step of the way there is a limited
resource that must be managed and in lock step with the others, yes, pun
intended. In effect, it involves the coordinated management of resources
all the way down.

For this first task you do not need to model every aspect of the lockes,
indeed you only need model its operation overall. Early on you learn
that there will be other software developers interacting with the system
and that not everyone is going to remember all the details of using the
resources of each component. Your task is to model the use of resources,
of system components, as simply as possible. You recognize that with all
the operational and sequencing details to be encapsulated, this is a
good use case for context managers.

Wondering about the consistent misspelling of the word lock? As an early
design decision we have moved to avoid overloading the term, which in
the context can be interpreted both as a verb and as a noun and thereby
cause confusion. For any instances of the verb use its usual spelling:
lock. For any instances of the noun use an alternative spelling: locke.
We have adopted this convention throughout the exercise.

Write a context manager class ``Locke`` to simulate the overall
functioning of the system. When the locke is entered it stops the pumps,
opens the doors, closes the doors, and restarts the pumps. Likewise when
the locke is exited it runs through the same steps: it stops the pumps,
opens the doors, closes the doors, and restarts the pumps. Don’t worry
for now that in the real world there are both upstream and downstream
doors, and that they should never be opened at the same time; perhaps
you’ll get to that later. During initialization the context manager class
accepts the locke’s capacity in number of boats. If someone tries to
move too many boats through the locke, anything over its established
capacity, raise a suitable error. Since this is a simulation you need do
nothing more than print what is happening with the doors and pumps, like
this:

.. raw:: html

   <div class="highlight-bash">

.. raw:: html

   <div class="highlight">

::

    "Stopping the pumps."
    "Opening the doors."
    "Closing the doors."
    "Restarting the pumps."

.. raw:: html

   </div>

.. raw:: html

   </div>

This is how you might interact with your Locke class.

.. raw:: html

   <div class="highlight-python3">

.. raw:: html

   <div class="highlight">

::

    small_locke = Locke(5)
    large_locke = Locke(10)
    boats = 8

    # Too many boats through a small locke will raise an exception
    with small_locke as locke:
        locke.move_boats_through(boats)

    # A lock with sufficient capacity can move boats without incident.
    with large_locke as locke:
        locke.move_boats_through(boats)

.. raw:: html

   </div>

.. raw:: html

   </div>

.. raw:: html

   </div>

.. raw:: html

   <div id="id1" class="section">

.. raw:: html

   </div>


.. raw:: html

   </div>
