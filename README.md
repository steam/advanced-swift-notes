# Advanced Swift Notes

A collection of notes on the excellent book [Advanced Swift](https://www.objc.io/books/advanced-swift/) by Chris Eidhof and Airspeed Velocity.

[Swift Style Guide](swift-style-guide.md)

###Array

`Array` is a value types but the items it contains _may_ not be. Assigning an `Array` to a new constant or variable creates a shallow copy unless the items held are also value types in which case it is a deep copy.

`SequenceType`'s `map`, `filter` and `reduce` remove the boiler plate code of a simliar operation allowing the unique transformation code to surface.

It is possible to use `sort` and `contains` in interesting ways. ie.

`people.contains { $0.age < 18 }`

Consider writing extensions for `SequenceType` when you find yourself writing collection lookup code.

Handy functions
```
extension SequenceType {
    func findElement (match: Generator.Element->Bool) -> Generator.Element? {
        for element in self where match(element) {
            return element
        }
        return nil
    }
}
```

Excerpt From: Chris Eidhof. “Advanced Swift.” iBooks. 

###Dictionary

Handy functions
```
extension Dictionary {
    mutating func merge<S: SequenceType
        where S.Generator.Element == (Key,Value)>(other: S) {
        for (k, v) in other {
            self[k] = v
        }
    }
}
```