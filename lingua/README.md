# RDF Lingua

RDF as the web lingua.

Lingua supports reasoning with forward rules described in RDF as
```
:rulename lingua:premis _:premisename;
    lingua:conclusion _:conclusionname.

_:premisename {
    RDF triples
}

_:conclusionname {
    RDF triples
}
```
and is able to give proof explanations as
```
:rulename lingua:bindings list of (var:name value) pairs.
```

A forward rule with `lingua:conclusion` false is an inference fuse.

Lingua also supports reasoning with backward rules described in RDF as
```
:rulename lingua:head _:headname;
    lingua:body _:bodyname.

_:headname {
    RDF triples
}

_:bodyname {
    RDF triples
}
```
and is able to give proof explanations as
```
:rulename lingua:bindings list of (var:name value) pairs.
```

Lingua also supports querying with queries described in RDF as
```
:queryname lingua:question _:questionname;
    lingua:answer _:answername.

_:questionname {
    RDF triples
}

_:answername {
    RDF triples
}
```
and is able to give proof explanations as
```
:queryname lingua:bindings list of (var:name value) pairs.
```

When `lingua:answer` is omitted it is the repetition of `lingua:question`.

The `lingua:` prefix is `<http://www.w3.org/2000/10/swap/lingua#>` and is rooted
in the "Semantic Web Area for Play" `http://www.w3.org/2000/10/swap/` URI.

The `var:` prefix is `<http://www.w3.org/2000/10/swap/var#>` and is used for
variables that are interpreted as universally quantified variables except for
forward rule conclusion-only variables which are interpreted existentially.
