HMC Debug System
================

Functions and methods to debug, analyze and plot the 2d variable(s) used in the Continuum Model.
The debugger can use two different engines to render the variable in a active plot: **Python** and **MatLab**.

Python
******

To debug variable 2d, user have to:
1) put the ForTran code in the source file where they need to verify one (or more) variable(s);
2) use the "hmc_debug_launcher" to install all dependencies and run the debugger.

The previous points are explained as follows:

**Python side**

.. code-block:: bash
	
    >> hmc_debug_launcher.sh

**Fortran side**

On the source Fortran file, put the following call:

.. code-block:: fortran

    call debug_2dVar(dble(var_data_2d), rows, cols, 1, 2)

MatLab
******

To debug variable 2d, user have to:
1) install MatLab on your machine;
2) put the ForTran code in the source file where they need to verify one (or more) variable(s);
3) use the MatLab command-line to run the debugger.

The previous points are explained as follows:

**MatLab side**

On the same folder of the Continuum source files:

.. code-block:: bash

    >> matlab -nosplash -nodesktop -r "debug_2dVar()"

From an external folder of the Continuum source files:

.. code-block:: bash

	>> matlab -nosplash -nodesktop -r "debug_2dVar(data_path)"

**Fortran side**

On the source Fortran file, put the following call:

.. code-block:: fortran

    call debug_2dVar(dble(var_data_2d), rows, cols, 1, 1)


