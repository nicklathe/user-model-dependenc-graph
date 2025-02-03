# User Model Method Dependency Graph

This is a graph that maps the method dependencies in the User model. Example:
`some_method_a` invokes `some_method_b` or `some_method_a -> some_method_b`.
This effort is to better understand how to modularize and and split up the User
model.

Leaf nodes (methods) in the graph are likely good candidates for moving to a
service (or query or policy) object that could be called from other methods,
whether they are defined in user.rb, or another place like a Rails Concern.

## Generating the Graph

* `brew install graphviz`
* `dot -Tpdf user-graph.dot > output/user-method-dependency-graph.pdf`
* You can export as other file types: `dot -T<file-type> user-method-dependency-graph.dot > output/user-model.<file-type>`
