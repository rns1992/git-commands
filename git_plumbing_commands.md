## Plumbing commands are not used on daily bases but are low level commands to understand how git works internally.

#### To get Hash of file. It uses SHA-1 algorithm to calculate hash for the content of file.
- `git hash-object {file-name}`

#### To see content type of hash.
- `git cat-file {hash} -t`

#### To see content of hash.
- `git cat-file {hash} -p`

Hash are stored in .git/object/{first 2 letters of hexa decimal of hash}/{remaining letter of hash}/{file}
