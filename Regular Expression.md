# Regular Expression - Search
> [!NOTE]  
> Information given below applies to the (Regular Expression Search mode) in npp

## Characters (`letters`, `digits`, `_`)

| **Pattern**              | **Description**                                          | **Example Matches**                             |
|--------------------------|----------------------------------------------------------|-------------------------------------------------|
| `\w`                     | Matches **1 character** (letters, digits, `_`)           | `a`, `b`, `_`                                   |
| `\wa`                    | Matches **1 character** followed by `a`                  | `aa`, `ba`, `ca`, `1a`, `2a`, `3a`, `_a`        |
| `\waa`                   | Matches **1 character** followed by `aa`                 | `aaa`, `baa`, `caa`, `1aa`, `2aa`, `3aa`, `_aa` |
| `\wabc`                  | Matches **1 character** followed by `abc`                | `aabc`, `babc`, `cabc`, `1abc`, `2abc`, `_abc`  |
| `\w\wa`                  | Matches **2 characters** followed by `a`                 | `aaa`, `bba`, `cca`, `1aa`, `22a`, `13a`, `_aa` |
| `\w+`                    | Matches **1 or more characters**                         | `apple`, `b_a_t`, `_cat`, `drum_`, `x`          |
| `\w+e`                   | Matches **1 or more characters ending with `e`**         | `apple`, `_voice`, `drive`, `l_i_k_e`, `_e`     |
| `a\w+e`                  | Matches **1 or more characters starting with `a` and ending with `e`**     | `apple`, `a_b_l_e`, `ace`     |

---

## Digits (`0-9`)

| **Pattern**              | **Description**                                      | **Example Matches**                          |
|--------------------------|------------------------------------------------------|----------------------------------------------|
| `\d`                     | Matches **1 digit**                                  | `1`, `2`, `3`                                |
| `\da`                    | Matches **1 digit** followed by `a`                  | `1a`, `2a`, `3a`                             |
| `\d\da`                  | Matches **2 digits** followed by `a`                 | `12a`, `34a`, `55a`                          |
| `\d+`                    | Matches **1 or more digits**                         | `0`, `12`, `345`, `6789`                     |
| `\d+0`                   | Matches **1 or more digits** ending with `0`         | `00`, `120`                                  |
| `0\d+9`                  | Matches **1 or more digits** starting with `0` and ending with `9`      | `01239`, `009`            |

---

### Whitespace (space, tab, newline)

| **Pattern**     | **Description**                                                 | **Example Matches**                          |
|-----------------|-----------------------------------------------------------------|----------------------------------------------|
| `\s`            | Matches any **whitespace character** (space, tab, newline)      | ` `, `\t`, `\n`                              |
| `\s+`           | Matches **1 or more whitespace characters**                     | ` `, `   `, `\n\t`                           |
| `\s?`           | Matches **0 or 1 whitespace character**                         | ` `, `a` (no whitespace between)             |
| `\S`            | Matches **any non-whitespace character**                        | `a`, `1`, `_`, `!`                           |
| `\S+`           | Matches **1 or more non-whitespace characters**                 | `hello`, `1234`, `@!_abc`                    |
| `\s\S`          | Matches a **whitespace** followed by a **non-whitespace**       | ` a`, `\n1`, `\tabc`                         |
| `\S\s`          | Matches a **non-whitespace** followed by **a whitespace**       | `a `, `1\t`, `_ \n`                          |

---

### Brackets

| **Pattern**     | **Description**                                       | **Example Matches**                          |
|-----------------|-------------------------------------------------------|----------------------------------------------|
| `\(` `\)`       | Matches **opening** / **closing** parenthesis         | `(`, `)`                                     |
| `\[` `\]`       | Matches **opening** / **closing** square bracket      | `[` ,`]`                                     |
| `\{` `\}`       | Matches **opening / **closing** curly brace           | `{` ,`}`                                     |
| `\(abc\)`       | Matches `abc` **enclosed in parenthesis**             | `(abc)`                                      |
| `(abc)`         | Matches `abc` **as a group** (captures the pattern)   | `abc`, `abcabc`, `abcabcabc`                 |
| `[abc]`         | Matches **any character inside the brackets**         | `a`, `b`, `c`                                |
| `{abc}`         | Matches `abc` **inside the curly brace**              | `{abc}`                                      |
| `a{2}`          | Matches **exactly 2  occurrences** of `a`             | `aa`                                         |
| `a{4}`          | Matches **exactly 4 occurrences** of `a`              | `aaaa`                                       |
| `a{2,}`         | Matches **2 or more occurrences** of `a`              | `aa`, `aaa`, `aaaa`                          |
| `a{4,}`         | Matches **4 or more occurrences** of `a`              | `baaaab`, `baaaaaa`, `baaaabaaab`            |
| `a{2,4}`        | Matches **2 to 4 occurrences** of `a`                 | `baaaab`, `baaaaaa`, `baaaabaaab`            |
| `[a-z]`         | Matches **any lowercase letters**                     | `a`, `b`, `c`                                |
| `[0-9]`         | Matches **any digit**                                 | `0`, `1`, `2`                                |
| `[^abc]`        | Matches **anthing except `a` `b` `c`**                | `0`, `1`, `c`, `d`                           |
| `(abc)+`        | Matches **one or more repetitions** of `abc`          | `abc`, `abcabc`, `abcabcabc`                 |

---

### Additional Notes:
**Context in Notepad++:**
   - Ensure that you are using "Regular Expression" in the Find/Replace dialogue box.
   - Regex patterns in Notepad++ are case-sensitive.
