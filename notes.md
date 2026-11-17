## Why avoid SELECT * in production?

- It returns columns we don't need, so the result has redundant data.
- It is slower. A real table may have many columns and millions rows, so reading and sending all of them wastes time and network bandwidth.
- It can break silently. If someone adds or reorthers columns later, code that uses SELECT * may receive the wrong data with any error.