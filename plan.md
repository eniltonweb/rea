1. **Add `isFreeObject()` and `isString()` to `MethodTable.java`**:
   - `isFreeObject()` will return `getBaseSize() < 0x10`.
   - `isString()` will check if `_manager.getStringMT()` is not null and its address matches the current MT's address.
2. **Update `MethodTableNet70.java` and `MethodTableNet80.java`**:
   - Replace `_baseSize < 0x10` with `isFreeObject()`.
   - Remove the `// TODO: abstract away` comments.
3. **Refactor `FrozenObjectAnnotator.java` (Optional but beneficial)**:
   - Change `mt.getAddress().getOffset() == _manager.getStringMT().getAddress().getOffset()` to `mt.isString()`.
4. **Pre-commit checks**:
   - Complete pre-commit steps to make sure proper testing, verifications, reviews and reflections are done.
