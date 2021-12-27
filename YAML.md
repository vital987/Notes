# WHAT IS

"YAML Ain't Markup Language". Human-readable data-serialization language. Commonly used for config files and in apps where data is stored or transmitted. Targets similar apps as XML but has minimal syntax intentionally different from SGML. Uses both Python-style indentation nesting (but tab character not allowed) and more compact format that uses `[]` for lists and `{}` for maps, making YAML 1.2 superset of JSON.

Natively encodes scalars (string, integer, and float), list, and associative array (map or dictionary). Allows custom data type.

Recommended file extension `.yaml`.

# COMMENT

```yaml
# this is a comment
```
# BASICS

```yaml
person:
  name: "Randy"  ## quotation optional; needed if string contains YAML-specific characters
  occupation: 'programmer'
  age: 37
  gpa: 3.8
  fav_num: 1e+10
  male: true
  birthday: 1983-02-26T05:36:58+0000  # ISO-8601
  flaws: null

  # array
  hobbies:
    - videogames
    - movies
    - lego building
  movies: ["The Matrix", "There's Something About Mary"]

  # map
  friends:
    - name: "Marshall"
    - age: 47
    - {name: "Adam", age: 38}
    -
      name: "Jane"
      age: 30

  # rendered as single long line
  description: >
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
    Mauris vel luctus orci. Proin in fermentum lectus. 
    Morbi molestie finibus ultrices. In vel dapibus metus, 
    vel molestie est. Fusce ac est vel ipsum luctus accumsan.

  # rendered with formatting preserved
  signature: |
    Randy
    iOS, Swift, React Native, JavaScript
    email - randy.hsiao@myemailhost.com
```
# CAST

```yaml
f: !!float 123  ## 123.0
s: !!str 123    ## "123"
```
# ANCHOR

```yaml
name: &name "Mike"  # define; anchor name doesn't have to be same as key
id: *name           # access; if value of key 'name' changed, this changes automatically
```

## KEY-VALUE PAIR

```yaml
base: &base
  bar1: 1

foo:
  <<: base
  bar2: 2
# foo has bar1 and bar2
```
