Demonstration of basic concepts and principles
- Modularization
- Architecture: ViewModel -> UseCase -> Repository + Logic + Calculator
- Performance

# My ideals
- Copying is better that coupling
- Naming might be subjectively bad, but it also can be objective inappropriate. Sometimes class or variable just
  should be renamed, and there is no space for debate
- `val`s and `var`s are properties, and their _accessors_ and _mutators_ are not your average `fun`ctions. They should
  only be used for _accessing_ and _mutating_
- `when`s over `enum`s and `sealed` classes whould always be exhaustive without `else` branch
- Not having `None` state in your `sealed` class coupled with _nullable_ value is better that having _non-null_ `sealed`
  class value with `None` state. This way it is easy to differenciate between use-cases when there might not be any value
  and when there is always some value

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
