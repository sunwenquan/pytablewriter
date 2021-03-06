.. _example-csv-table-writer:

Write a CSV table
----------------------------

|CsvTableWriter| class can write a Comma-Separated Values (CSV) table to the |stream| from a matrix of data.

.. code-block:: python
    :caption: Sample code that writes a CSV table

    import pytablewriter

    writer = pytablewriter.CsvTableWriter()
    writer.header_list = ["int", "float", "str", "bool", "mix", "time"]
    writer.value_matrix = [
        [0,   0.1,      "hoge", True,   0,      "2017-01-01 03:04:05+0900"],
        [2,   "-2.23",  "foo",  False,  None,   "2017-12-23 45:01:23+0900"],
        [3,   0,        "bar",  "true",  "inf", "2017-03-03 33:44:55+0900"],
        [-10, -9.9,     "",     "FALSE", "nan", "2017-01-01 00:00:00+0900"],
    ]
    
    writer.write_table()


.. code-block:: none
    :caption: Output of CSV

    "int","float","str","bool","mix","time"
    0,0.1,"hoge",True,0,"2017-01-01 03:04:05+0900"
    2,-2.2,"foo",False,,"2017-12-23 12:34:51+0900"
    3,0.0,"bar",True,inf,"2017-03-03 22:44:55+0900"
    -10,-9.9,"",False,nan,"2017-01-01 00:00:00+0900"


.. _example-tsv-table-writer:

Write a TSV table
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

|TsvTableWriter| class can write a Tab-Separated Values (TSV) table to the |stream| from a matrix of data.

.. code-block:: python
    :caption: Sample code that writes a TSV table
    
    import pytablewriter

    writer = pytablewriter.TsvTableWriter()
    writer.header_list = ["int", "float", "str", "bool", "mix", "time"]
    writer.value_matrix = [
        [0,   0.1,      "hoge", True,   0,      "2017-01-01 03:04:05+0900"],
        [2,   "-2.23",  "foo",  False,  None,   "2017-12-23 45:01:23+0900"],
        [3,   0,        "bar",  "true",  "inf", "2017-03-03 33:44:55+0900"],
        [-10, -9.9,     "",     "FALSE", "nan", "2017-01-01 00:00:00+0900"],
    ]
    
    writer.write_table()

.. code-block:: none
    :caption: Output of TSV

    "int"	"float"	"str"	"bool"	"mix"	"time"
    0	0.1	"hoge"	True	0	"2017-01-01 03:04:05+09:00"
    2	-2.2	"foo"	False		"2017-12-23 45:01:23+0900"
    3	0.0	"bar"	True	inf	"2017-03-03 33:44:55+0900"
    -10	-9.9	""	False	nan	"2017-01-01 00:00:00+09:00"
