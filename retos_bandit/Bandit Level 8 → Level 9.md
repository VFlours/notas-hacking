
## Goal

The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## data access
bandit8
TESKZC0XvTetK0S9xNwm25STk5iWrBvP

## Solution

```
bandit8@bandit:~$ sort data.txt | uniq -c
     10 18DyjwhN856SsMx8bNrFSvr6rJxNQKhE
     10 1iyGemEgn3qUOOFcAJyGPHOiewqZyp1y
     10 2CQ5DQRdtoe9Ft8YpMHqCwQcN1Bk9lCI
     10 365RauAVsFlxktPMpoLtIf1uxijU1TfV
     10 4K2MoVHd1gXfoOdDjvlaRxFNZwmi4A4C
     10 52p0CnGhAvm4m3fPKqz9mTxVDeVYCvnG
     10 5Y76FifuxKStZi4CVovF2uPhgLrZnLzG
     10 7A4l2BI3lPJgNdWAmyXAGlfB8uvCQLX0
     10 8cxarYi5VoKRj3lzo2baLOJaMgUtzoRH
     10 97Qwmy18JE8aGIud1stpTsOrOtUMHeGI
     10 9d8exmGtSsGcU1gz6HmqTfSxmnmI4FBo
     10 A16BW831T94qcsYcGDSkgzYhxnX2xUdK
     10 aAd8RbcAAGVRifo0gE2x1nPIGH2fjgZi
     10 ahwL1iJ5EDLt9wpBjrP2DY8pv6FLdrLy
     10 AiYd84lOOVTA4gqJPX7f6DH8eG3zwq1W
     10 aniL5AEkrKcj4mFR1ujwPZdtF4z1SAin
     10 b0XUx8jfeWYAUGlnOGGAyVRxdNziM4SF
     10 bJDV41So5UyGPR98w9x5pX6nqWsOU2ra
     10 br26ueVSoLeZd8HqErTJpNVCtwFufHGO
     10 BVego1OuHFYy1glUiCH3m5dQxEPV8D6d
     10 bWO8QplAdUvLTPoI07UdQc6zKvON0WS3
     10 cEqNrEqHVIIi9fQKdcvAxaip1brmsSxT
     10 Dml3j9ydZQj13Q6xVRPHVuMhD9pt0NbT
     10 drJxnp5fJxeVRYlCldsIEtrEEwBdyRIL
     10 eJZcdtHKg9jLpvpK9v31Fj1opqlA1A9k
      1 EN632PlfYiZbn3PhVK3XOGSlNInNE00t

bandit8@bandit:~$ sort data.txt | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
bandit8@bandit:~$

```

## notes

-c --> cuenta el numero de ocurrencias de la linea
-sort --> se pone el sort para que al contar las ocurrencias al estar en orden no se pierda el conteo progresivo.

## references


