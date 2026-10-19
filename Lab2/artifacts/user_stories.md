# User stories

#### Story-001 - Gather data as an outsider to the system

**As a** Guest, **I want to** make a research, **so that** I can gather data for my research

```gherkin
Scenario: Registration
    Given : I do not have an account on platform
    When : I register using my email
    Then : The system creates and gives me an accout

Scenario: Improving account to researcher as regular user
    Given : I am registered user
    And : Do not have researcher account
    When : I apply for improvement of account to researcher
    Then : My account becomes researcher
    And : Now I am able to create and edit my researches

Scenario: Improving account to researcher as researcher
    Given : I am registered user
    And : Have researcher account
    When : I apply for improvement of account to researcher
    Then : I recieve messege that I am already a researcher

Scenario: Creating research
    Given : I am registered user
    And : Have researcher account
    When : I create reserach
    Then : There is new research that I have control over

Scenario: Creating form
    Given : I am registered user
    And : Have researcher account
    And : Have a not closed research
    When : I create form
    Then : Research I created it for gets this form
```

#### Story-002 - Complete research

**As a** Registered user, **I want to** complete a research, **so that** world would be a little better

```gherkin
Scenario: Research search
    Given : I am registered user
    When : I look for researches I can complete
    Then : The system gives me list of new researches that I haven't completed yet

Scenario: Look for forms
    Given : I am registered user
    When : I look for forms on particular research
    Then : The system gives me list of all forms related to this form that I can complete

Scenario: Completing form
    Given : I am registered user
    When : I complete a form
    Then : The system accepts my answer
    And : Marks this form as completed

Scenario: Completing form second time
    Given : I am registered user
    And : I have already completed some form
    When : I try complete this form a second time
    Then : The system does not allow me to complete it second time
    And : Informs me that i have alredy completed it
```

#### Story-003 - Complete research

**As a** Researcher, **I want to** get final data from a research, **so that** I could finish my research paper

```gherkin
Scenario: Closing research
    Given : I am registered user
    And : Have researcher account
    And : Have a research with some amount of answers
    When : I close the research
    Then : The research closes
    And : The research does not allow any new answers to it's forms

Scenario: Export data
    Given : I am registered user
    And : Have researcher account
    And : Have a research with some amount of answers
    When : I try to export data
    Then : The system gives me file with all of the answers data
```
