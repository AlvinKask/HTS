# HTS
- [otsitavad.txt](https://github.com/AlvinKask/HTS/files/11583785/otsitavad.txt)
- [wordlist.txt](https://github.com/AlvinKask/HTS/files/11583789/wordlist.txt)
#

'''
# Loeme sisse wordlist'i faili
with open("wordlist.txt", "r") as wordlist_file:
    wordlist = wordlist_file.read().splitlines()

# Loeme sisse otsitavate faili
with open("otsitavad.txt", "r") as otsitavad_file:
    otsitavad = otsitavad_file.read().splitlines()

# Loome tühja sõnastiku otsitavate ja algandmete sidumiseks
sidumine = {}

# Võrdleme ja seome sõnad kokku
for sõna in otsitavad:
    segatud_tähed = "".join(sorted(sõna))  # Sorteerime segatud tähed
    for algandmete_sõna in wordlist:
        if sorted(algandmete_sõna) == sorted(segatud_tähed):
            sidumine[sõna] = algandmete_sõna
            break

# Prindime välja vastavused
vastused = [sidumine[otsitav] for otsitav in otsitavad if otsitav in sidumine]
vastused_str = ", ".join(vastused)
print(vastused_str)
'''
