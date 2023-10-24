Branch names will structured with the following format:
"category/project/branch-name"

**Categories**

Category names should be 3 or 4 characters long.

- "updt": Branch updates limited to include changes that primarily
  reflect new date ranges for outputs.

<!-- -->

- "feat": For new features, indicators, new functionality. These are
  branches that add something to either an existing indicator (e.g.,
  adding hospital stays as an initial placement) or add a new indicator
  (e.g., median time in care for kids in care at the end of the year).

<!-- -->

- "fix" (Let's pick one): For fixing some specific problem/error that
  needs to be addressed quickly. These branches should refer to anything
  incorrect in our code base that either brakes programs or produces
  incorrect outputs.

<!-- -->

- "mod": Modification/addition to an existing program not intended to
  add new aspects for the indicator. The modifications can range from a
  simple adding a code to be counted in a placement type to big changes
  to the macro that generates the output.

<!-- -->

- "junk": Just casual branches for tinkering with programs that may or
  may not ever be merged into master. These branches may be disregarded,
  or renamed to "feat" branches.

<!-- -->

- "wip": These are "Work in Progress" branches that represent
  not-so-easy to fix problems or new features that might span multiple
  quarters.

**Project**

- "bh": BH Project

<!-- -->

- "cerap": Cerap Project

<!-- -->

- blank?: In some cases, a branch may produce code that applies to
  multiple projects. In this case, the branch name could be omitted, or
  perhaps replaced with "all".

<!-- -->

- etc...

**Branch-Name**

- "YYYYqn-optional-descriptor": Branches will begin with a four digit
  year, followed by a quarter indicator, such as "2020q1", if
  appropriate. More specific individualized quarterly branches may
  contain names such as "2020q1-feature-description".

<!-- -->

- "feature-description": If it is not appropriate for a branch to
  contain a year and quarter specifier, then the name may simply be
  comprised of a few descriptive words that briefly describe the purpose
  of the branch, such as "refactors-foo-macro".

**Examples**

- updt/bh/2020q1
- updt/bh/2020q1-new-race-codes
- feat/bh/2020q1-new-indicator-indj99
- bug/bh/2020q1-bad-race-codes
- junk/bh/db-table-simple-compare