PyLadies - lekce seznamy
========================

CZ.NIC Praha 24.5.2016

Toto je učesaný přepis příkazů, které jsem promítal na hodině. V interaktivním pythonu puštěného v příkazové řádce.

Seznam (`list`)
---------------

Uděláme pár proměnných, které budou obsahovat seznamy.

    tel_seznam = []
    bucket_list = ['naucit se python', 'darovat krev', 'vycestovat na island']

Poslední dva záznamy vypíšu stejným krájecím zápisem, jako u řetězců.

    bucket_list[-2:]

Krátkým forcyklem můžeme hezky vypsat celý seznam.

    for goal in bucket_list:
        print('nez umru chci', goal)

Pomocí metody append můžeme přidávat záznamy na konec seznamu.

    tel_seznam.append('Terka 666 888 777')
    tel_seznam.append('Vasek 789456 123 4')
    tel_seznam.append('oskar 777 777 777')

Oskara jsme omylem napsali špatně, jak to opravíme?

Tohle nezafunguje, dojde tím k sečtení seznamů (hrůza ze stringu se stal list písmenek!).

    tel_seznam[-1:] = 'Oskar 777 777 777'

Takhle to taky nejde, sice jsme pomocí indexů na písmenku, které chceme opravit, ale řetězec se nedá měnit (narozdíl od pole).

    tel_seznam[-1][0] = 'O'

Takhle to půjde, nahradíme v seznamu poslední prvek celým opraveným řetězcem.

    tel_seznam[-1] = 'Oskar 777 777 777'

Seznamy se dají sčítat, to se někdy hodí.

    tel_seznam.append('Bozena 123 456 789')
    druhy_seznam = ['Lenka 456 789 456', 'Petr 741 852 963']
    tel_seznam + druhy_seznam

Můžeme si výsledný seznam uložit do nové proměnné...

    spojeny_seznam = tel_seznam + druhy_seznam

Nebo za použití metody extend připojíme druhý seznam na konec prvního.

    tel_seznam.extend(druhy_seznam)

Metoda pro řazení se hodí taky.

    tel_seznam.sort()
    # vypiseme jmena hezky pod sebe
    for jmeno in tel_seznam:
        print(jmeno)

Řadit se dá i v opačném gardu.

    vysledky_zavodu = ['2 nahoda', '5 Petr', '8 Honza', '4 Zbysek']
    vysledky_zavodu.sort(reverse=True)

V seznamech můžou být jednotlivé prvky různého typu.

    bordel = ['Honza', 3.1415, 666, 'ahoj', [1,2,3], 'cau']

Vždy si u seznamu můžeme zjistit počet prvků.

    len(bordel)

Jen když chceme prvky řadit, musíme zařídit (napsat svojí funkci), aby se daly vzájemně porovnat, proto tohle skončí chybou.

    bordel.sort()

Jak se dá uložit například historie příkazů nebo prohlížených stránek na webu? No přeci do seznamu. Jak to funguje si ukážeme na batohu. Nejdřív je prázdný, pak do něj skládáme věci.

    batoh = []
    batoh.append('boty')
    batoh.append('spacak')
    batoh.append('obleceni')
    batoh.append('svacina')
    batoh.append('celovka')

Pomocí metody pop() můžeme vynad poslední vloženou věc.

    # Tohle vrátí čelovku.
    batoh.pop()
    # Pro změnu něco zase vložíme
    batoh.append('plastenka')

Pomocí metody index(), zjistíme, na které pozici je určitá věc, ale pozor, zjistíme pouze první výsktyt i když někde dál v seznamu se může prvek znovu objevit.

    bordel.index('cau')

Metoda count() zjistí, kolikrát je daný prvek v seznamu.

    bordel.count('cau')

Cvičení
-------

Máme dva řetězce `a` a `t`, `a` obsahuje vyjmenovaná slova, `t` je text, ve kterém máme zjistit počet různých vyjmenovaných slov.

Řešení: Oba texty převedeme na seznamy pomocí metody split(), potom v cyklu otestujeme každé vyjmenované slovo, jestli náhodou není v textu.

    a = 'pýcha, pytel, pysk, netopýr, slepýš, pyl, kopyto, klopýtat, třpytit se, zpytovat, pykat, pýr, pýřit se, čepýřit se'
    t = 'netopýr nemá kopyto'
    # takhle to nevypada dobre, jsou tam carky a mezery
    vp = list(a)
    # tohle je lepší
    vp = a.split(', ')

    # vyresetujeme počítadlo
    celkem = 0
    # pro kazde vyjmenovane slovo testujeme a pri shode napocitame
    for slovo in t.split():
        if slovo in vp:
            celkem += 1

K zamyšlení: Jak zjistíme počet vyjmenovaných slov v textu, pokud by se opakovala.
(odpověd: když místo vyjmenovaných slov dáme do for cyklu zdrojový text a do podmínky vyjmenované slova)


N-tice (tuple)
--------------

Tuple, česky "entice", je zjednodušeně řečeno to samé, jako seznam (list) ale nedá se měnit její obsah (přidávat a odebírat věci z baťohu).

Tuple píšeme do kulatých závorek.

    kody_zemi = ('cz', 'sk', 'us', 'fr', 'de')

Některé funkce mohou vracet i více návratových hodnot, dokonce se to dá použít i v cyklu. Tady vypíšeme pořadové číslo a položku seznamu pomocí vestavěné funkce enumerate.

    for id, vec in enumerate(bordel):
        print(id, vec)

Cvičení
-------

Zkusíme sestrojit hrací pole pro 2D piškvorky.

Řešení: Uděláme seznam, seznamů, pro začátek na pevno 3x3

Jako lenoši uděláme jeden prázndý řádek hracího pole a namnožíme si ho (nejlépe bychom ho měli plnit pomocí for cyklu).

    a = [ '-', '-', '-']
    b = list(a)
    c = list(a)

Hrací plocha je pak seznam z těchto seznamů.

    hp = [a,b,c]

Abychom hrací pole vypsali, musíme použít dva vnořené for cykly (u funkce print si musíme poručit, kdy zalomí řádek a kdy ne)

    for radek in hp:
        for znak in radek:
            print(znak, end='')
        print()

Na konkrétní hodnotu hracího políčka se dostaneme pomocí postupného indexování

    hp[1][2]
    
A to můžeme použít i pro zápis nové hodnoty. Takhle vložíme doprostřed hrací plochy křížek (vyměníme prvek v seznamu za řetězec 'x'.

    hp[1][1] = 'x'
