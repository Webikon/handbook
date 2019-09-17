# BDD

## Gherkin

The three steps, the context, the action, and the outcome. It's just written out in a way that is machine parseable, but it's meant to be business readable. So a human can read it as if it was a document.

> Let's zoom in. The problem I'm talking about is scheduling training. I do a lot of training and either we have a training course with not enough people, so we need to cancel it or we have too many people. So as a trainer I should be able to cancel courses or schedule new ones and I can identify the business rules. This stuff at the top of the feature file is just human readable text to explain to a person.
>
> So the rules are, when I make a course, it has size limits, there's a sort of threshold where the course becomes viable, and when we reach a maximum class size, you can't sign up to that course anymore. And then I come up with some examples and I write them out. The `Background` is context that's common to all of the examples in the file. So we talk about context using the `Given` keyword:
>
> > Given "BDD for Beginners" was proposed with a class size of 2 to 3 people
>
> So that's the context. The first example is, a course doesn't get enough enrollments so it's not viable. When only Alice enrolls in the course, then this course won't be viable, easy to understand. Hopefully.
>
> This is an example where the course gets enough enrollments. So Alice is already enrolled in the course, that's the context. When Bob enrolls, that's the action. Then the course becomes viable, the course will be viable because it was proposed to the size of two to three. And enrollments have stopped when the class size is reached. Given that Alice, Bob and Charlie have already enrolled in the course, when Derek tries to enroll in the course, he can't enroll.

```text
Feature: Scheduling a training course

  As a trainer
  In order to be able to cancel courses or schedule new ones
  I should be able to specify a maximum and minimum class size

  Rules:
    - Course is proposed with size limits
    - When enough enrolments happen, course is considered viable
    - When maximum class size is reached, further enrolments are not allowed

  Background:
    Given "BDD for Beginners" was proposed with a class size of 2 to 3 people

  Scenario: Course does not get enough enrolments to be viable
    When only Alice enrols on this course
    Then this course will not be viable

  @important
  Scenario: Course gets enough enrolments to be viable
    Given Alice has already enrolled on this course
    When Bob enrols on this course
    Then this course will be viable

  Scenario: Enrolments are stopped when class size is reached
    Given Alice, Bob and Charlie have already enrolled on this course
    When Derek tries to enrol on this course
    Then he should not be able to enrol

```

It costs something to write them out in this detailed format and think about how much detail you're gonna include. When you're going to build the system soon you write them out in this kind of **Given**, **When**, **Then** format and you show them to the person you had the conversation with and says, this is what we talked about. So whoever learned the most in the conversation can write out these scenarios, so this is what we talked about in the room. Please validate that. Let's just double check. You don't do this, you don't write them out in this detail in advance for everything.

> _As a \[role\]_  
> _I want \[feature\]_  
> _So that \[benefit\]_

```text
Feature: Installation
  In order to use the plugin
  As an administrator
  I need to be able to activate and deactivate the plugin

  Scenario: see the plugin in the plugins admin screen
    Given I am logged in as an administrator
    When I go to the plugins administration page
    Then I should see the "Codeception Beta 22" plugin

  Scenario: activate the plugin
    Given I am logged in as an administrator
    When I go to the plugins administration page
    And I activate the "Codeception Beta 22" plugin
    Then I should see the "Codeception Beta 22" plugin activated

  Scenario: deactivate the plugin
    Given I am logged in as an administrator
    And the "Codeception Beta 22" plugin is activated
    When I go to the plugins administration page
    And I deactivate the "Codeception Beta 22" plugin
    Then I should see the "Codeception Beta 22" plugin deactivated
```

```text
Feature: home
  In order to read the latest posts
  As a visitor
  I need to see the latest posts on the homepage

  Scenario: the home page will show the latest published posts in descending order
    Given I have post in database
      | post_type | post_title | post_status |
      | post      | Post 1     | publish     |
      | post      | Post 2     | publish     |
      | post      | Post 3     | publish     |
      | post      | Post 4     | private     |
      | post      | Post 5     | draft       |
      | post      | Post 6     | publish     |
    When I am on page "/"
    Then I see number of elements ".post" and expected 4
```

```text
Feature: Wordpress Gherkin Custom Post Types
  In order to have a common Wordpress BDD framework
  As a Wordpress plugin
  I should be able to create CPTs related to the gherkin language
  
Scenario: The plugin is activated
  Given the plugin is installed
  When the plugin is activated
  Then the CPTs "pickles" are created
  And the various pickle types are created

Scenario: the various pickle types are created
  Given the plugin is activated
  When the user sees a list of pickle types
  Then there will be pickle-type "terms"
  And there will be pickle-type "actors"
```

```text
Feature: Product basket
  In order to buy products
  As a customer
  I need to be able to put interesting products into a basket

  Rules:
  - VAT is 20%
  - Delivery for basket under £10 is £3
  - Delivery for basket over £10 is £2

  Scenario: Buying a single product under £10
    Given there is a "Sith Lord Lightsaber", which costs £5
    When I add the "Sith Lord Lightsaber" to the basket
    Then I should have 1 product in the basket
    And the overall basket price should be £9

  Scenario: Buying a single product over £10
    Given there is a "Sith Lord Lightsaber", which costs £15
    When I add the "Sith Lord Lightsaber" to the basket
    Then I should have 1 product in the basket
    And the overall basket price should be £20

  Scenario: Buying two products over £10
    Given there is a "Sith Lord Lightsaber", which costs £10
    And there is a "Jedi Lightsaber", which costs £5
    When I add the "Sith Lord Lightsaber" to the basket
    And I add the "Jedi Lightsaber" to the basket
    Then I should have 2 products in the basket
    And the overall basket price should be £20
```

Gherkin for your accessibility scenarios

```text
Scenario: Skip to content link
    Given I am on the homepage
    When I select the ‘Skip to content’ link
    Then the main content has keyboard focus

Scenario: Video captions
    Given I am on the video page
    When I select the ‘play’ button
    And I turn on captions
    Then the correct closed captions display throughout the video
```

## Resources

* [https://automationpanda.com/bdd/](https://automationpanda.com/bdd/)
* [https://dannorth.net/introducing-bdd/](https://dannorth.net/introducing-bdd/)
* [https://codeception.com/docs/07-BDD](https://codeception.com/docs/07-BDD)
* [https://cucumber.io/docs/gherkin/reference/](https://cucumber.io/docs/gherkin/reference/)
* [https://wpbrowser.wptestkit.dev](https://wpbrowser.wptestkit.dev)

