Simplistic Java model classes for NGINX config files


# Goals

* POJO style
* Read-Modify-Write
* Change only what is known, esp.:
    * Don't change unknown tokens
    * Don't change comments or whitespace
    * This does _not_ have to be perfect for whitespace between known expressions

# Non-Goals

* Validation
* To Be Fast
* Access to all aspects of the config
* Build config from scratch

# Alternatives

* [odiszapc/nginx-java-parser](https://github.com/odiszapc/nginx-java-parser)
    * Doesn't retain empty lines
    * Not typesafe

# Restrictions

Anything between `upstream` and `server` directives will be moved after the last `server` directive. 
This kind of moving also happens to unknown expressions within known blocks.
