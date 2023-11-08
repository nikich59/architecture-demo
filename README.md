Todo: add code samples

Demonstration of basic concepts and principles
- Modularization: Plugins & ModuleApi & ModuleDependencies
- Scoped Tasks
- Dependency Injection
- Architecture: ViewModel -> UseCase -> Repository + Logic + Calculator
- Performance
- Unit tests
- Code generation from specs. One-of included
- MVVM with single state val and all-Flow data management
- Animations: both inside screens and between screens
- Blur
- Nested scroll for AppBarLayout on menu 
- Project: Address, Catalog, Menu, Cart, Checkout, Order Tracking. Address is used on different screens. Cart is shown on catalog

# My ideals
- Copying is better that coupling. Do not reuse data models, copy-paste them
- Great backend contracts enable great architecture. Bad contract forbids great architecture. As front-end developers, out professional duty is to insist that our contracts:
  - Describe what _must_ be done, not what _can_ be done
  - Are as close to plain English description of the contents of the screen as possible
  - Use polymorphic models instead of one-size-fits-all models with dozens of optional fields
  - Lack any implicit linking: if two fields are always either both null or both non-null, they must both be required fields in another model
  - Have decent names to every field and value. Enum values must __never__ be `Integers`
  - When adding new feature which data can be retrived from already existing fields, we should still add brand new field with a model that contains all the required data for the feature. Even if heavy copy-pasting will be needed
- Naming might be subjectively bad, but it also can be objective inappropriate. Sometimes class or variable just
  should be renamed, and there is no space for debate
- There is almost never any need to shorten variable, function or class names
- Cases when lines of code are better merged into less lines of code are almost non-existent 
- `val`s and `var`s are properties, and their _accessors_ and _mutators_ are not your average `fun`ctions. They should
  only be used for _accessing_ and _mutating_
- `when`s over `enum`s and `sealed` classes whould always be exhaustive without `else` branch
- Not having `None` state in your `sealed` class coupled with _nullable_ value is better that having _non-null_ `sealed`
  class value with `None` state. This way it is easy to differenciate between use-cases when there might not be any value
  and when there is always some value
- How many `value` classes do I want? Yes

# What I personally can't stand
- Many programmers must have come from economics background because they _save_. Saving symbols and lines of code
  is a crime againts your current and future colleagues
- Compiler is great at type inference, but people are not. Think about people, not compiler, when writing your code
  The code
  ```
  val accessToken: String? = authRepository.getAccessToken()
  ```
  is __not__ worse than
  ```
  val accessToken = authRepository.getAccessToken()
  ```
- `SOLID`, `YAGNI`, `DRY`, `KISS` and the others are just catch phrases. You should always understand what _advantages_
  and _drawbacks_ your solution has over alternatives, and how well it will withstand future changes. Using catch-phrases
  like mentioned ones does not count as an argument
