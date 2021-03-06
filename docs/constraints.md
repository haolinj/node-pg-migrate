# Constraint Operations

### `pgm.addConstraint( tablename, constraint_name, expression )`

> Add a named column constraint - [postgres docs](http://www.postgresql.org/docs/current/static/sql-altertable.html)

**Arguments:**

- `tablename` _[string]_ - name of the table to alter
- `constraint_name` _[string]_ - name for the constraint
- `expression` _[string or object]_ - constraint expression (raw sql) or definition:
  - `check` _[string]_ - sql for a check constraint
  - `unique` _[string or array of strings or array of array of strings]_ - names of unique columns
  - `primaryKey` _[string or array of strings]_ - names of primary columns
  - `exclude` _[string]_ - sql for an exclude constraint
  - `deferrable` _[boolean]_ - flag for deferrable table constraint
  - `deferred` _[boolean]_ - flag for initially deferred deferrable table constraint
  - `foreignKeys` _[object or array of objects]_ - foreign keys specification
    - `columns` _[string or array of strings]_ - names of columns
    - `references` _[string]_ - names of foreign table and column names
    - `referencesConstraintName` _[string]_ - name of the created constraint
    - `onDelete` _[string]_ - action to perform on delete
    - `onUpdate` _[string]_ - action to perform on update
    - `match` _[string]_ - `FULL` or `SIMPLE`

**Aliases:** `createConstraint`
**Reverse Operation:** `dropConstraint`

---

### `pgm.dropConstraint( tablename, constraint_name, options )`

> Drop a named column constraint - [postgres docs](http://www.postgresql.org/docs/current/static/sql-altertable.html)

**Arguments:**

- `tablename` _[string]_ - name of the table to alter
- `constraint_name` _[string]_ - name for the constraint
- `options` _[object]_ - options:
  - `ifExists` _[boolean]_ - drops constraint only if it exists
  - `cascade` _[boolean]_ - drops also dependent objects

### `pgm.renameConstraint( tablename, old_constraint_name, new_constraint_name )`

---

> Rename a constraint - [postgres docs](http://www.postgresql.org/docs/current/static/sql-altertable.html)

**Arguments:**

- `tablename` _[string]_ - name of the table to alter
- `old_constraint_name` _[string]_ - current constraint name
- `new_constraint_name` _[string]_ - new constraint name

**Reverse Operation:** same operation in opposite direction
