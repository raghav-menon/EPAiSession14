## Project

For this project you have 4 files containing information about persons.

The files are:
* `personal_info.csv` -   personal information such as name, gender, etc. (one row per person)
* `vehicles.csv` -   what vehicle people own (one row per person)
* `employment.csv` -   where a person is employed (one row per person)
* `update_status.csv` -   when the person's data was created and last updated

Each file contains a key, `SSN`, which **uniquely** identifies a person.

This key is present in **all** four files.

You are guaranteed that the same SSN value is present in **every** file, and that it only appears **once per file**.

In addition, the files are all sorted by SSN, i.e. the SSN values appear in the same order in each file.

#### Goal 1

Your first task is to create iterators for each of the four files that contained cleaned up data, of the correct type (e.g. string, int, date, etc), 
and represented by a named tuple.

For now these four iterators are just separate, independent iterators.

#### Goal 2

Create a single iterable that combines all the columns from all the iterators.

The iterable should yield named tuples containing all the columns.
Make sure that the SSN's across the files match!

All the files are guaranteed to be in SSN sort order, and every SSN is unique, and every SSN appears in every file.

Make sure the SSN is not repeated 4 times - one time per row is enough!

#### Goal 3

Next, you want to identify any stale records, where stale simply means the record has not been updated since 3/1/2017 (e.g. last update date < 3/1/2017). 
Create an iterator that only contains current records (i.e. not stale) based on the `last_updated` field from the `status_update` file.

#### Goal 4

Find the largest group of car makes for each gender.

Possibly more than one such group per gender exists (equal sizes).

### Hints

You will not be able to use a simple split approach here, as I explain in the video.

Instead you should use the `csv` module and the `reader` function.

### cast  

Function for type casting to the required datatype

### cast_row

Function which takes a list of elements and send it to the above function for typecasting

### read_file

Function whic reads the file depending on the file name and returns an iterator for the particular file

### sorting

Function to sort depending on the key provided. Takes an iterator and sorts it based on the key provided

### merge

Function to merge multiple nameduple objects. Merges by converting it to dictionary

### combiter

Function to combine multiple iterators. Each iterator provides namedtuple when processed

### filiter

Function to filter the data based on the date. Provides a generator which contains elements which are above the given date

### counter

Function which counts the type of cars driven by men and women and provided individual reverse sorted dictionary. This takes in
a combined iterator

The deep note link is https://deepnote.com/project/Session14-m9wU7bauRrCyBA2QurYGMw/%2FSession14.ipynb
