==============
Input Adapters
==============

ChatterBot's input adapters are designed to allow a chat bot to have a
versatile method of receiving or retrieving input from a given source.

.. toctree::
   :maxdepth: 1

   create-an-input-adapter

The goal of an input adapter is to get input from some source, and then
to convert it into a format that ChatterBot can understand. This format
is the :ref:`Statement <conversation_statements>` object found in ChatterBot's
`conversation` module.

Default input adapter
=====================

.. autofunction:: chatterbot.input.InputAdapter

The default input adapter for ChatterBot allows the chat bot to accept a
number of different input types using the same adapter. This adapter accepts
strings_, dictionaries_ and :ref:`Statements <conversation_statements>`.

.. code-block:: python

   chatbot = ChatBot(
       "My ChatterBot",
       input_adapter="chatterbot.input.InputAdapter"
   )

Terminal input adapter
======================

.. autofunction:: chatterbot.input.TerminalAdapter

The input terminal adapter allows a user to type into their terminal to
communicate with the chat bot.

.. code-block:: python

   chatbot = ChatBot(
       "My ChatterBot",
       input_adapter="chatterbot.input.TerminalAdapter"
   )

Gitter input adapter
====================

.. autofunction:: chatterbot.input.Gitter

.. code-block:: python

   chatbot = ChatBot(
       "My ChatterBot",
       input_adapter="chatterbot.input.Gitter",
       gitter_api_token="my-gitter-api-token",
       gitter_room="my-room-name",
       gitter_only_respond_to_mentions=True,
   )

Mailgun input adapter
=====================

.. autofunction:: chatterbot.input.Mailgun

The Mailgun adapter allows a chat bot to receive emails using
the `Mailgun API`_.

.. literalinclude:: ../../examples/mailgun.py
   :language: python

.. _microsoft-input-adapter:

Microsoft Bot Framework input adapter
=====================================

.. autofunction:: chatterbot.input.Microsoft

This is an input adapter that allows a ChatterBot instance to communicate
through `Microsoft`_ using *direct line client* protocol.

Be sure to also see the documentation for the :ref:`Microsoft output adapter <microsoft-output-adapter>`.

.. code-block:: python

   chatbot = ChatBot(
       "My ChatterBot",
       input_adapter="chatterbot.input.Microsoft",
       directline_host="https://directline.botframework.com",
       directline_conversation_id="IEyJvnDULgn",
       direct_line_token_or_secret="RCurR_XV9ZA.cwA.BKA.iaJrC8xpy8qbOF5xnR2vtCX7CZj0LdjAPGfiCpg4Fv0",
   )

.. _strings: https://docs.python.org/2/library/string.html
.. _dictionaries: https://docs.python.org/2/tutorial/datastructures.html#dictionaries
.. _`Mailgun API`: https://documentation.mailgun.com/api_reference.html
.. _Microsoft: https://docs.botframework.com/en-us/restapi/directline/#/Conversations
