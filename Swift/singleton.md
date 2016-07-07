# Singleton Concept
In software engineering, the singleton pattern is a design pattern that restricts the instantiation of a class to one object.

This is useful when exactly one object is needed to coordinate actions across the system.


# Singleton in Swift
```swift
class Singleton {
	struct Static {
		static var instance: Singleton? = nil
			static var token : dispatch_once_t = 0
	}

	class func sharedInstance() -> Singleton! {
		dispatch_once( &Static.token ) {
			Static.instance = self()
		}

		return Static.instance!
	}

	required init() {

	}
}
```

# References
[Singleton pattern](https://en.wikipedia.org/wiki/Singleton_pattern)
