Clean Code
==========



When writing code, what are the values you must balance?

1. Functionality
  * The code must accomplish the task.
1. Readable
  * Your code should use clearly written function and variable names.
    * Functions
      * Named with verbs indicating what they *do*.
      * No more than 3 words.
      * Examples:
        * addCertificate
        * removeWrapper
        * createClone
    * Variables and properties which are booleans should be labeled as statements in the positive form. 
      * isOn
      * hasCertificate
      * canInitialize
      * passedTests
1. Easy to reason about
  * Functions are single purpose.
  * Complexity is refactored into layers.
  * If a function accomplishes many tasks, it does so by invoking other, more specific functions.
  * No function mixes minute detail with multiple function invocations.
  * When someone else is reading your code, they should be able to understand what is happening with no or minimal context beyond the section of code at which they are looking.
1. Compatability
  * The code should be compatable with the browsers or machines of your target market.  Not supporting older browsers or hardware may be acceptable and it may not, but you must at least have this in mind.
1. 







1. Reusability













1. Performance