# iOS-links
Interesting findings related to iOS

## [Protocol composition for dependency injection](http://merowing.info/2017/04/using-protocol-compositon-for-dependency-injection)

```swift
protocol Has{Dependency} {
  var {dependency}: {Dependency} { get }
}

class FooViewModel {
  typealias Dependencies = HasImageProvider & HasArticleProvider

  let dependencies: Dependencies

  init(..., dependencies: Dependencies)
}

struct AppDependency: HasImageProvider, HasArticleProvider, HasPersistanceProvider {
  let imageProvider: ImageProvider
  let articleProvider: ArticlesProvider
  let persistanceProvider: PersistenceProvider
}
```
