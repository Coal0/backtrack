backtrack
---------

backtrack is a simple logging tool for Python 3.
Features:

* Simple
* MIT licensed
* Supports all file descriptor 'writable' objects.
* Supports colored output
* Supports three useful formatting keys (datetime, unixtime, file)

To install backtrack, run

.. code-block:: shell
    
    pip install backtrack

or

.. code-block:: shell

    pip3 install backtrack

Documentation
#############

``configure(file_descriptor=sys.stdout, level=INFO, use_color=False)``:

Set logging options.

Parameters:

* ``file_descriptor``: A file descriptor with a ``write`` method. Defaults to ``sys.stdout``.
* ``level``: An integer (any of 0, 1, 2 for INFO, WARNING and ERROR respectively). Defaults to INFO.
* ``use_color``: Whether or not to use ANSI color codes. Defaults to False.

Returns:

* ``None``

Raises:

* ``RuntimeError`` if ``file_descriptor`` has no ``write`` method.
* ``ValueError`` if ``level`` is not any of INFO, WARNING, ERROR.

|
|

``error(message)``:

Write a level 2 (ERROR) message to the file.

Parameters:

* ``message``: The message to write to the file.

Returns:

* ``None``

|
|

``info(message)``:

Write a level 0 (INFO) message to the file.

Parameters:

* ``message``: The message to write to the file.

Returns:

* ``None``

|
|

``warning(message)``:

Write a level 1 (WARNING) message to the file.

Parameters:

* ``message``: The message to write to the file.

Returns:

* ``None``

|
|

The ``message`` argument passed to the logging functions can contain these formatting keys:

* ``{datetime}``: The date and time as reported by ``time.ctime``.
* ``{unixtime}``: The unix timestamp as reported by ``time.time``.
* ``{file}``: The calling file.
