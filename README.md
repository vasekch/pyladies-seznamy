'''
tel_seznam = []
nakupni_seznam = []
bucket_list = ['naucit se python', 'darovat krev', 'vycestovat na island']
bucket_list
bucket_list[-2:]
for goal in bucket_list:
    print('nez umru chci', goal)
tel_seznam
tel_seznam.append('Terka 666 888 777')
tel_seznam.append('Vasek 789456 123 4')
tel_seznam.append('oskar 777 777 777')
tel_seznam
tel_seznam[-1:] = 'Oskar 777 777 777'
tel_seznam
tel_seznam = []
tel_seznam
tel_seznam.append('Terka 666 888 777')
tel_seznam.append('Vasek 789456 123 4')
tel_seznam.append('oskar 777 777 777')
tel_seznam[-1]
tel_seznam[2]
tel_seznam
tel_seznam[-1]
tel_seznam[-1][0]
tel_seznam[-1][0] = 'O'
tel_seznam[-1] = 'Oskar 777 777 777'
tel_seznam
tel_seznam.append('Bozena 123 456 789')
druhy_seznam = ['Lenka 456 789 456', 'Petr 741 852 963']
tel_seznam
druhy_seznam
tel_seznam + druhy_seznam
spojeny_seznam = tel_seznam + druhy_seznam
spojeny_seznam
tel_seznam
druhy_seznam
spojeny_seznam
tel_seznam.extend(druhy_seznam)
tel_seznam
tel_seznam.sort()
tel_seznam
for jmeno in tel_seznam:
    print(jmeno)
tel_seznam.sort(~)
vysledky_zavodu = ['2 nahoda', '5 Petr', '18 Honza', '4 Zbysek']
vysledky_zavodu
vysledky_zavodu.sort()
vysledky_zavodu
vysledky_zavodu[0] = '8 Honza'
vysledky_zavodu
vysledky_zavodu.sort()
vysledky_zavodu
vysledky_zavodu.sort(reverse=True)
vysledky_zavoduA
vysledky_zavodu
bordel = ['Honza', 3.1415, 666, 'ahoj', [1,2,3], 'cau']
len(bordel)
bordel.sort()
bordel
del bordel[0]
bordel
batoh = []
batoh
batoh.append('boty')
batoh.append('spacak')
batoh.append('obleceni\')
batoh.append('obleceni')
batoh.append('svacina\')
batoh.append('svacina')
batoh
batoh.append('celovka')
batoh
batoh.pop()
batoh
batoh.append('plastenka')
batoh
1/0
batoh
batoh.pop()
bordel
bordel.append('neco')
bordel
del bordel[0]
bordel
bordel.index('ahoj')
bordel
bordel.index('cau')
bordel.append('cau')
bordel
bordel.index('cau')
bordel.count('cau')
bordel
a = 'pýcha, pytel, pysk, netopýr, slepýš, pyl, kopyto, klopýtat, třpytit se, zpytovat, pykat, pýr, pýřit se, čepýřit se'
a
a.__type__
a
t = 'netopýr nemá kopyto'
t
vp = list(a)
vp
a.split()
a.split(',')
a
t
a.split(', ')
vp = a.split(', ')
vp
celkem = 0
t
for slovo in t.split():
    if slovo in vp:
        celkem += 1
celkem
for i in range(10):
    print(i)
for i in range(10):
    print(i)
for id, vec in enumerate(bordel)
for id, vec in enumerate(bordel):
    print(id, vec)
a = [ '-', '-', '-']
b = a
a
b
a[1] = 'x'
a
b
b = list(a)
a
b
a[1] = '-'
a
b
c = list(a)
a
b
c
hp = [a,b,c]
bordel
hp
for i in hp:
    print(i)
for radek in hp:
    for znak in radek:
        print(znak, end='')
    print()
hp
hp[1][2]
hp[1][1]
'''
