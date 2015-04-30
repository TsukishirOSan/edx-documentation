.. _Dropdown:

#####################
Dropdown Problem
#####################

Dropdown problems allow the learner to choose from a collection of answer
options, presented as a dropdown list. Unlike multiple choice problems, which
have answers that  are always visible directly below the question, dropdown
problems do not show answer choices until the learner clicks the dropdown
arrow.

.. image:: ../../../shared/building_and_running_chapters/Images/DropdownExample.png
 :alt: A problem component with 3 dropdown problems, 2 marked correct and 1
     incorrect

********************************
Creating a Dropdown Problem
********************************

You can create dropdown problems in the Simple Editor or in the Advanced Editor.

.. note:: Problems must include accessible labels. An accessible label generally 
 includes the text of the main question in your problem. To add an accessible
 label, you use the Simple Editor and surround the text of the label with angle
 brackets pointed toward the text (>>label text<<).
 
.. _Use the Simple Editor to Create a Dropdown Problem:

========================================================================
Use the Simple Editor to Create a Dropdown Problem
========================================================================

To use the Simple Editor to create a dropdown problem, follow these steps.

#. In the unit where you want to create the problem, under **Add New
   Component** select **Problem**.
#. From the list of **Common Problem Types**, select **Dropdown**.
#. Select **Edit**. The Simple Editor opens with an example problem. In the
   editor, you replace the sample problem text with your own text.
#. Determine the text that expresses the question you want learners to answer,
   and then use two sets of angle brackets (>><<) to surround that text. This
   question text is the accessible label for the problem.
#. Edit your problem text to place all of the possible answers on the same
   line, separated by commas.
#. Select all of the answer options, and then select **Dropdown** in
   the editing toolbar. A double set of brackets ([[ ]]) appears to surround
   the answer options.
#. To identify the problem's answer, locate that answer inside the brackets
   and surround the correct answer with parentheses.
#. To provide an explanation, select the explanation text and then select 
   **Explanation** from the toolbar. ``[explanation]`` appears before
   and after the explanation text.
#. Select **Settings** and provide an identifying **Display Name** for the
   problem.
#. Specify options for the problem. For more information, see :ref:`Problem
   Settings`.
#. Select **Save**.

For the example problem illustrated above, the following text displays in the
problem component.

::

    >>What type of data are the following?<<

    Age:
    [[Nominal, Discrete, (Continuous)]]
    Age, rounded to the nearest year:
    [[Nominal, (Discrete), Continuous]]
    Life stage - infant, child, and adult:
    [[(Nominal), Discrete, Continuous]]

========================================================================
Use the Advanced Editor to Create a Dropdown Problem 
========================================================================

To use the Advanced Editor to create a dropdown problem, follow these steps.

#. Follow steps 1-3 for creating the problem in the :ref:`Simple Editor<Use
   the Simple Editor to Create a Dropdown Problem>`. 
#. Select **Advanced Editor**, and then replace the existing XML with your
   own code. An example follows.

**Problem Code:**

.. code-block:: xml

  <problem>
  <p>
    <em>This exercise first appeared in HarvardX's PH207x Health in Numbers: Quantitative Methods in Clinical &amp; Public Health Research course, fall 2012.</em>
  </p>
  <p>What type of data are the following?</p>
  <p>Age:</p>
  <optionresponse>
    <optioninput options="('Nominal','Discrete','Continuous')" correct="Continuous" label="Age"/>
  </optionresponse>
  <p>Age, rounded to the nearest year:</p>
  <optionresponse>
    <optioninput options="('Nominal','Discrete','Continuous')" correct="Discrete" label="Age, rounded to the nearest year"/>
  </optionresponse>
  <p>Life stage - infant, child, and adult:</p>
  <optionresponse>
    <optioninput options="('Nominal','Discrete','Continuous')" correct="Nominal" label="Life stage"/>
  </optionresponse>
  </problem>

.. _Dropdown Problem XML:

************************
Dropdown Problem XML
************************

========
Template
========

.. code-block:: xml

  <problem>
  <p>
    Problem text</p>
  <optionresponse>
    <optioninput options="('Option 1','Option 2','Option 3')" correct="Option 2" label="label text"/>
  </optionresponse>
    <solution>
      <div class="detailed-solution">
      <p>Explanation or Solution Header</p>
      <p>Explanation or solution text</p>
      </div>
    </solution>
  </problem>

.. code-block:: xml

  <problem>
   <p>Problem text</p>
    <optionresponse>
     options="('A','B')"
      correct="A"/>
      label="label text"
    </optionresponse>
   
    <solution>
      <div class="detailed-solution">
      <p>Explanation or Solution Header</p>
      <p>Explanation or solution text</p>
      </div>
    </solution>
  </problem>

========
Tags
========

* ``<optionresponse>`` (required): Indicates that the problem is a dropdown problem.
* ``<optioninput>`` (required): Lists the answer options.

**Tag:** ``<optionresponse>``

Indicates that the problem is a dropdown problem.

  Attributes

  (none)

  Children

  ``<optioninput>``  

**Tag:** ``<optioninput>``

Lists the answer options.

  Attributes

  .. list-table::
     :widths: 20 80

     * - Attribute
       - Description
     * - options (required)
       - Lists the answer options. The list of all answer options is
         surrounded by parentheses. Individual answer options are surrounded
         by single quotation marks (') and separated by commas (,).
     * - correct (required)
       - Indicates whether an answer is correct. Possible values are "true"
         and "false". Only one **correct** attribute can be set to "true".
     * - label (required)
       - Specifies the name of the response field.
  
  Children

  (none)