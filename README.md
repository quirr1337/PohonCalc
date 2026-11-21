# PohonCalc – kalkulačka elektrických pohonov

**PohonCalc** je jednoduchá webová aplikácia vytvorená v low-code platforme **Mendix**.
Slúži na rýchly výpočet dvoch základných veličín elektrických pohonov:
**výkonu trojfázového motora** a **krútiaceho momentu na hriadeli**.

Projekt vznikol ako **Zadanie 1: Low-Code** v predmete *Programovacie techniky*.

## Funkcie

- hlavná obrazovka s navigáciou,
- **Výpočet 1** – výkon trojfázového motora,
- **Výpočet 2** – krútiaci moment na hriadeli,
- okno **O programe**,
- kontrola vstupov (účinník 0 – 1, otáčky > 0),
- návrat z každého okna späť na hlavnú obrazovku.

## Okná aplikácie

| Okno | Popis |
|---|---|
| Hlavná obrazovka | názov aplikácie, tlačidlá Výpočet 1, Výpočet 2 a O programe |
| Výpočet 1 | zadanie U, I, cos φ → výpočet výkonu P |
| Výpočet 2 | zadanie P, n → výpočet krútiaceho momentu M |
| O programe | účel aplikácie, vzorce, autor |

## Použité vzorce

### 1. Výkon trojfázového motora

P = √3 · U · I · cos φ / 1000 [kW]

| Veličina | Význam | Jednotka |
|---|---|---|
| U | združené napätie | V |
| I | prúd | A |
| cos φ | účinník | – |
| P | činný výkon | kW |

**Príklad:** U = 400 V, I = 15 A, cos φ = 0,85 → **P ≈ 8,833 kW**

### 2. Krútiaci moment na hriadeli

M = 9550 · P / n [N·m]

| Veličina | Význam | Jednotka |
|---|---|---|
| P | výkon na hriadeli | kW |
| n | otáčky | ot/min |
| M | krútiaci moment | N·m |

**Príklad:** P = 7,5 kW, n = 1450 ot/min → **M ≈ 49,397 N·m**

## Štruktúra riešenia v Mendixe

- **Entity:** `VypocetVykonu`, `VypocetMomentu` (neperzistentné)
- **Mikroflowy:** `ACT_VypocetVykonu_Calculate`, `ACT_VypocetMomentu_Calculate`
- **Stránky:** `Home_Web`, `Vypocet1_Vykon`, `Vypocet2_Moment`, `OPrograme`
- **Dizajn:** Atlas UI (karty, responzívna mriežka)

## Ako spustiť

1. Nainštalujte **Mendix Studio Pro** (verzia 10 alebo novšia).
2. Stiahnite súbor `PohonCalc.mpk` z tohto repozitára.
3. V Studio Pro zvoľte **File → Import App Package…**
4. Spustite aplikáciu cez **Run → View App**.

## Snímky obrazovky

![Hlavná obrazovka](‪<img width="1280" height="610" alt="photo_2026-11-21_20-24-23" src="https://github.com/user-attachments/assets/ae03b172-6456-497f-a535-1c4cc8b30895" />).
![Výpočet 1](‪<img width="1280" height="615" alt="photo_2026-11-21_20-24-29" src="https://github.com/user-attachments/assets/134e2514-2a09-469b-adc3-ab79babb1812" />
)
![Výpočet 2](<img width="1280" height="571" alt="photo_2026-11-21_20-24-32" src="https://github.com/user-attachments/assets/4ed1d13f-efef-4ab7-b9a8-c0bfa743a17d" />
)
![O programe](<img width="1280" height="559" alt="photo_2026-11-21_20-24-36" src="https://github.com/user-attachments/assets/a73188c1-8918-4183-9297-4b7e20a1e4b0" />
).

## Použitý AI nástroj

Pri tvorbe aplikácie bol použitý AI asistent **Claude (Anthropic)** cez **Claude Code**.
Pomáhal s návrhom štruktúry aplikácie, výberom vzorcov, vytvorením entít,
mikroflowov a stránok v Mendixe a s textom tohto README.
Výsledok bol skontrolovaný a otestovaný autorom.

## Autor

- **Meno:** [Rostyslav Kharlashko]
- **Skupina:** [St 11:05. sk 3]
- **Predmet:** Programovacie techniky, 2026
