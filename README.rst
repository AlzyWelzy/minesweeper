Minesweeper
===========

This Python module contains a ``Board`` class that represents a
Minesweeper game. The ``Board`` class has the following attributes and
methods:

Attributes
----------

-  ``dim_size``: an integer representing the number of rows and columns
   in the board. The board will be a square with dimensions
   ``dim_size x dim_size``.
-  ``num_bombs``: an integer representing the number of bombs that are
   placed on the board.
-  ``board``: a 2D list representing the board, with the bombs randomly
   placed.
-  ``dug``: a set of tuples representing the locations that have been
   dug. Initially, this is an empty set.

Methods
-------

``__init__(self, dim_size, num_bombs)``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This is the constructor for the ``Board`` class. It takes in two
arguments:

-  ``dim_size``: an integer representing the number of rows and columns
   in the board. The board will be a square with dimensions
   ``dim_size x dim_size``.
-  ``num_bombs``: an integer representing the number of bombs that
   should be placed on the board.

The constructor initializes the ``dim_size``, ``num_bombs``, ``board``,
and ``dug`` attributes. It creates a new board with the
``make_new_board`` method and assigns values to the empty spaces with
the ``assign_values_to_board`` method.

``make_new_board(self)``
^^^^^^^^^^^^^^^^^^^^^^^^

This is a helper method that constructs a new board with the bombs
placed randomly. It returns the constructed board as a 2D list.

``assign_values_to_board(self)``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This method assigns a number (0-8) to each empty space on the board,
representing the number of neighboring bombs. It does this by calling
the ``get_num_neighboring_bombs`` method for each empty space on the
board.

``get_num_neighboring_bombs(self, row, col)``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This method takes in a row and column index and returns the number of
bombs in the eight neighboring positions. It does this by iterating
through the eight positions and incrementing a count for each bomb
found.

``dig(self, row, col)``
^^^^^^^^^^^^^^^^^^^^^^^

This method takes in a row and column index and “digs” at that location
on the board. If the location contains a bomb, the game is over.
Otherwise, the location is added to the ``self.dug`` set and the method
returns the value at that location on the board.

Usage
-----

To use the ``Board`` class, import it from this module and create a new
instance with the desired dimensions and number of bombs:

.. code:: python

   from minesweeper import Board

   board = Board(dim_size=8, num_bombs=10)
