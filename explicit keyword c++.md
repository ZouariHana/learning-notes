explicit prevents a constructor or conversion operator from being used for unintended implicit conversions.

**Example of implicit conversions**

```cpp
struct XMLDoc {
    xmlDocPtr raw;

    // NOT explicit → allows implicit conversion from xmlDocPtr
    XMLDoc(xmlDocPtr p) : raw(p) {}
};

void use(XMLDoc);

xmlDocPtr raw = xmlReadMemory("<x/>", 4, nullptr, nullptr, 0);

use(raw);        // OK: xmlDocPtr implicitly converted to XMLDoc via constructor
XMLDoc d = raw;  // OK: copy-initialization uses converting constructor
XMLDoc e{raw};   // OK: direct-list-initialization also allowed
```

- The single-argument constructor without `explicit` is a *converting constructor*, so the compiler inserts it automatically where an `XMLDoc` is expected.
- Marking it `explicit` would make `use(raw)` and `XMLDoc d = raw;` errors, requiring `XMLDoc(raw)` or `static_cast<XMLDoc>(raw)` instead.
