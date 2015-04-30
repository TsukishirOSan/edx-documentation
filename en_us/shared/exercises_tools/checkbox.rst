.. _Checkbox:

##################
Checkbox Problem
##################

In checkbox problems, the learner selects one or more options from a list of
possible answers. The learner must select all the options that apply to answer
the problem correctly. Each checkbox problem must have at least one correct
answer.

.. image:: ../../../shared/building_and_running_chapters/Images/CheckboxExample.png
 :alt: A checkbox problem with four options, 2 of which are required for the
     correct answer

****************************
Creating a Checkbox Problem
****************************

You can create checkbox problems in the Simple Editor or in the Advanced Editor.

.. note:: Problems must include accessible labels. An accessible label generally 
 includes the text of the main question in your problem. To add an accessible
 label, you use the Simple Editor and surround the text of the label with angle
 brackets pointed toward the text (>>label text<<).

.. _Use the Simple Editor to Create a Checkbox Problem:

======================================================
Use the Simple Editor to Create a Checkbox Problem
======================================================

To use the Simple Editor to create a checkbox problem, follow these steps.

#. In the unit where you want to create the problem, under **Add New
   Component** select **Problem**.
#. From the list of **Common Problem Types**, select **Checkboxes**.
#. Select **Edit**. The Simple Editor opens with an example problem. In the
   editor, you replace the sample problem text with your own text.
#. Determine the text that expresses the question you want learners to answer,
   and then use two sets of angle brackets (>><<) to surround that text. This
   question text is the accessible label for the problem.
#. Edit your text to place each answer option on a separate line.
#. Select your set of answer options, and then select **Checkboxes** from the
   toolbar. A pair of brackets appears next to each answer choice.
#. To identify each correct answer, add an **x** between the brackets for that option.
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

.. code-block:: xml

    Learning about the benefits of preventative healthcare can be particularly 
    difficult. >>Check all of the reasons below why this may be the case.<<

    [x] A large amount of time passes between undertaking a preventative measure and seeing the result. 
    [ ] Non-immunized people will always fall sick. 
    [x] If others are immunized, fewer people will fall sick regardless of a particular individual's choice to get immunized or not. 
    [x] Trust in healthcare professionals and government officials is fragile. 

.. please do not line wrap this example:

    [explanation]
    People who are not immunized against a disease may still not fall sick from the disease. If someone is trying to learn whether or not preventative measures against the disease have any impact, he or she may see these people and conclude, since they have remained healthy despite not being immunized, that immunizations have no effect. Consequently, he or she would tend to believe that immunization (or other preventative measures) have fewer benefits than they actually do.
    [explanation]


========================================================================
Use the Advanced Editor to Create a Checkbox Problem 
========================================================================

To use the Advanced Editor to create a checkbox problem, follow these steps.

#. Follow steps 1-3 for creating the problem in the :ref:`Simple Editor<Use
   the Simple Editor to Create a Checkbox Problem>`.
#. Select **Advanced Editor**, and then replace the existing XML with your own
   marked up text. An example follows.

.. code-block:: xml

  <problem>
    <p>Learning about the benefits of preventative healthcare can be particularly difficult. Check all of the reasons below why this may be the case.</p>

  <choiceresponse>
    <checkboxgroup label="Check all of the reasons below why this may be the case">
      <choice correct="true"><text>A large amount of time passes between undertaking a preventative measure and seeing the result.</text></choice>
      <choice correct="false"><text>Non-immunized people will always fall sick.</text></choice>
      <choice correct="true"><text>If others are immunized, fewer people will fall sick regardless of a particular individual's choice to get immunized or not.</text></choice>
      <choice correct="true"><text>Trust in healthcare professionals and government officials is fragile.</text></choice>
    </checkboxgroup>
  </choiceresponse>

   <solution>
   <div class="detailed-solution">
   <p>Explanation</p>
   <p>People who are not immunized against a disease may still not fall sick from the disease. If someone is trying to learn whether or not preventative measures against the disease have any impact, he or she may see these people and conclude, since they have remained healthy despite not being immunized, that immunizations have no effect. Consequently, he or she would tend to believe that immunization (or other preventative measures) have fewer benefits than they actually do.</p>
   </div>
   </solution>
  </problem>

.. _Checkbox Problem XML:

****************************
Checkbox Problem XML 
****************************

============
Template
============

.. code-block:: xml

  <problem>
    <p>Question text</p>

  <choiceresponse>

  <checkboxgroup label="label text">
  <choice correct="false"><text>Answer option 1 (incorrect)</text></choice>
  <choice correct="true"><text>Answer option 2 (correct)</text></choice>
  </checkboxgroup>
  </choiceresponse>

   <solution>
   <div class="detailed-solution">
   <p>Solution or Explanation Heading</p>
   <p>Solution or explanation text</p>
   </div>
   </solution>

  </problem>

======
Tags
======

* ``<choiceresponse>`` (required): Specifies that the problem contains options
  for learners to choose from.
* ``<checkboxgroup>`` (required): Specifies that the problem is a checkbox problem.
* ``<choice>`` (required): Designates an answer option.

**Tag:** ``<choiceresponse>``

Specifies that the problem contains options for learners to choose from.

  Attributes

  (none)

  Children

  ``<checkboxgroup>``

**Tag:** ``<checkboxgroup>``

Specifies that the problem is a checkbox problem.

  Attributes

  .. list-table::
     :widths: 20 80

     * - Attribute
       - Description
     * - label (required)
       - Specifies the name of the response field.

  Children

  ``<choice>`` 

**Tag:** ``<choice>``

Designates an answer option.

  Attributes

  .. list-table::
     :widths: 20 80

     * - Attribute
       - Description
     * - true (at least one required)
       - Indicates a correct answer. For checkbox problems, one or more
         ``<choice>`` tags can contain a correct answer.
     * - false (at least one required)
       - Indicates an incorrect answer.

  Children
  
  (none)
