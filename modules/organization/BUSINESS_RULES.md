Rule 9

Organization UUID is never exposed internally.

Database joins always use BIGINT.

Public APIs always use UUID.
Rule 10

Organization Slug is immutable after activation.
Rule 11

Organization Display Name may change.

Organization UUID never changes.

Rule 12

Organization Type cannot change once Active.

Administrator must archive and recreate if legal type changes.