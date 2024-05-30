---
layout: default
title: Clojure for Statistics
parent: Miscellaneous
---
# Creating a simple project using Clojure Tools

## Clojure Tools
Clojure Tools (tools.deps) is a collection of Clojure command line utilities for developing with Clojure. This fills the same role (more or less) as Leiningen, which is an unofficial build/development tool for Clojure. While Leiningen is a great tool, tools.deps will be covered here as it is easier to load dependencies directly from Git platforms (as opposed to compiled jar files on Clojars or Maven Central).

### Installation
To install Clojure CLI, see the official instructions: [https://clojure.org/guides/install\_clojure](https://clojure.org/guides/install_clojure)

## Creating a project folder
A basic project folder really only needs a `src` directory and a `deps.edn` file. A `config.edn` may be needed if using the [clj-toolbox](https://github.com/cfrc-uiuc/clj-toolbox) library.

```shell
$ mkdir test-project
$ cd test-project
$ mkdir -p src/test_project # Note this is a "_", not a "-"
$ touch deps.edn
$ echo '{:paths ["src"]}' >> deps.edn
$ touch config.edn
```

If using clj-toolbox, edit deps.edn to add clj-toolbox to the dependency map. Be sure to alter the below information to include the latest version of clj-toolbox:

```clojure
{:paths ["src"]
 :deps {
        io.github.cfrc-uiuc/clj-toolbox {:git/url "git+ssh://git@github.com/cfrc-uiuc/clj-toolbox"
                                         :git/tag "0.1.3"
                                         :git/sha "ac43cfd"}
        }
 }
```

You may also need to edit config.edn to add credential information for clj-toolbox (see the clj-toolbox repository's `config.edn.example`):

```clojure
{
:db-spec {
         :user ""
         :password ""
    }
}
```

Lastly, create your primary namespace file, such as `src/test_project/core.clj`:

```clojure
(ns test-project.core
    (:gen-class)
    (:require [clj-toolbox.core :as tb]
              [clj-toolbox.db :as db]))
```

At this point, you may want to create a new Git repository and add your new project to it.

## Choosing an editor

This is beyond the scope of this document, but the popular choices are Emacs and VSCode. For more information, see:

- [Spacemacs](https://www.spacemacs.org/)
- [Practicali Spacemacs](https://practical.li/spacemacs/)
- [VSCode](https://code.visualstudio.com/)
- [VSCodium (Open Source VSCode)](https://vscodium.com/)
- [VSCode Calva](https://calva.io/)
