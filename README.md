# password-wise
Pragmatic, list fueled, password strength estimator.

password-wise aims to rate good (easy to memorize) human passwords. An input list doesn't have to be extensive - the matching is not exact. It just needs a sufficient sample of common words and patterns (few 100 KB might suffice).

2 scores are estimated:
- Normalized length to density ratio. E.g. '12345678' or 'qwertyqwerty' gets a score close to 0; combinations of uncommon words - around 1; the value will exceed 1 for more random (difficult to remember) inputs
- Entropy. 'passwordqwerty123456' should be below 20 bits (weighted permutations); SHA1 hash is ca. 160 bits

Random capitalization is hard to remember and is not counted towards entropy to discourage its use. A simple capitalization scheme is fine.

I'm aware of dropbox/zxcvbn. This one is aimed at backend use. It is memory efficient. Large pattern tree with 100 million nodes fits into 800 MB RAM. There are no language restrictions. Any region and keyboard layout is incorporated by adding a relevant password list.
