Web2py.test
===========


An example of how to test an Web2py Application.

I use py.test [1] to test this application, but the concept can be applied in unittest and nose, too.

Tested in Web2py v2.7.4 and v2.9.5

IMPORTANT: I recommend you work with virtualenv to give you more freedom. It's not required, but strongly recommended.



## Stepping into

The procedure to run tests present for this application is:


1. Create a new virtualenv. Let's call it bla:

        $ cd ~
        $ mkdir -p virtualenvs/bla
        $ cd virtualenvs/bla
        $ virtualenv .

1. Enter into it:

        $ source bin/activate

1. Now your prompt should look like this:

        (bla)username@yourmachine:~$

1. Install py.test just in your virtualenv:

        $ pip install pytest

1. Download latest web2py stable:

        $ wget http://www.web2py.com/examples/static/web2py_src.zip

1. Unzip it:

        $ unzip web2py_src.zip

1. Now you must see web2py dir created inside your current dir.
1. Enter into it:

        $ cd web2py

1. Get the latest web2py.test:

        $ git clone https://github.com/viniciusban/web2py.test.git applications/people

1. You must see the people dir inside your applications directory.
1. Start Web2py development server:

        $ python web2py.py -a my_password --nogui &

1. Run tests:

        $ py.test -x -v -s applications/people/tests

Voilà!




## Understanding

To understand the method used to allow running tests, refer to web2py/applications/people/tests/conftest.py

Read web2py/applications/people/models/db.py to see how to make your application know she is running under the test environment.

Test cases are in web2py/applications/people/tests subdirs.


There are 3 important parts in this application:

1. tests/conftest.py -> configure test environment.
1. modules/web2pytest/web2pytest.py -> test infrastructure.
1. models/db.py -> ask web2pytest about tests and create db accordingly.


Links used in this doc:

- [1] http://pytest.org

